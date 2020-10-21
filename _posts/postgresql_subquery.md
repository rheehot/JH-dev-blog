---
title: PostgreSQL 서브쿼리
date: 2020-10-21
tags:
  - postgresql
  - db
  - 서브쿼리
keywords:
  - postgresql
  - db
  - 서브쿼리
---

## 서브쿼리 란?

서브쿼리는 쿼리문 내에서 메인 쿼리가 아닌 하위에 존재하는 쿼리를 말한다.

```db
SELECT
  AVG(RENTAL_RATE)
FROM
  FILM
```

## 설명

### 2.99 <-- 쿼리를 통한 결과

```db
SELECT
        FILM_ID,
        TITLE,
        RENTAL_RATE
FROM
        FILM
WHERE RENTAL_RATE > 2.99;
```

```db
SELECT
        FILM_ID,
        TITLE,
        RENTAL_RATE
FROM
        FILM
WHERE RENTAL_RATE >
(
        SELECT
                AVG(RENTAL_RATE)
        FROM FILM
)
```

### 인라인 뷰 서브쿼리 사용 ( A와 B에 넣어서 인라인 뷰)

```db
SELECT
        FILM_ID,
        TITLE,
        RENTAL_RATE
FROM
        FILM A,
        (
                SELECT
                        AVG(RENTAL_RATE)
                FROM FILM
        ) B
WHERE A.RENTAL_RATE > B.AVG_RENTAL_RATE;
```

### 스칼라 서브쿼리 활용 (<-- 아직 이해 못함..ㅠㅜ)

```db
SELECT
        FILM_ID,
        TITLE,
        RENTAL_RATE
FROM
        (
                SELECT
                        A.FILM_ID,
                        A.TITLE,
                        A.RENTAL_RATE,
                        (
                                SELECT
                                        AVG(L.RENTAL_RATE)
                                FROM
                                        FILM L
                        ) AS AVG_RENTAL_RATE
                FROM FILM A
        )A
WHERE
        A.RENTAL_RATE > A.AVG_RENTAL_RATE;
```

데이터 결과가 동일하면 -> 동일한 쿼리 입니다:)

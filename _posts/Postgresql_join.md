---
title: PostgreSQL JOIN
date: 2020-10-21
tags:
  - postgresql
  - db
  - join
keywords:
  - postgresql
  - db
  - join
---

### 테이블 조인

```db
SELECT user_id, created_at::date ca
FROM picture
LEFT OUTER JOIN love
  on picture.id = love.id
  where picture.created_at > love.created_at
  and love.created_at::date > '2020-10-21'

GROUP BY ca
```

### 테이블 3개 조인

```db
SELECT user_id, created_at::date ca
FROM picture
LEFT OUTER JOIN love on picture.id = love.id
LEFT OUTER JOIN sweet on picture.id = sweet.id
  where picture.created_at > love.created_at
  and love.created_at::date > '2020-10-21'

GROUP BY ca
```

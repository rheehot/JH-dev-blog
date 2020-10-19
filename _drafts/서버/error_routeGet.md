---
title: Error: Route.get() requires a callback function but got a [object Object]
date: 2020-10-16
---

## Error: Route.get() requires a callback function but got a [object Object]

get reguire 로 연결만 시켜두고 내용이 없어서 에러!

콘솔에 에러메세지 끝까지 읽어보는 습관 들이자

```js
router.get('/getScrapLoveCountByMonth', require('./getScrapLoveCountByMonth'));

router.get('/getScrapLoveUserCount', require('./getScrapLoveUserCount'));
// router.get('/getScrapLoveUserCountByTime', require('./getScrapLoveUserCountByTime'));
// router.get('/getScrapLoveUserCountByWeek', require('./getScrapLoveUserCountByWeek'));
// router.get('/getScrapLoveUserCountByMonth', require('./getScrapLoveUserCountByMonth'));
```

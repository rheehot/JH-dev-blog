# React render 중 map대신 for문 쓰고 싶을 때

props로 받아오는 데이터가 배열이 아닌 그냥 숫자일 때 그만큼 반복해야 할 때 사용

```js
{
	[...Array(num)].map((n, index) => {
		return <div>// 이렇게 하면 num만큼 반복하며 렌더링할 수 있다.</div>;
	});
}
```

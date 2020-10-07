# 리액트에서 자주 쓰는 if문 작성 패턴 5개

참고: https://online.codingapple.com/unit/react-if-else-patterns-enum-switch-case/

##

### 1. 컴포넌트 안에 쓰는 if/else

```js
function Component() {
	if (true) {
		return <p>참이면 보여줄 HTML</p>;
	} else {
		return null;
	}
}
```

```js
function Component() {
	if (true) {
		return <p>참이면 보여줄 HTML</p>;
	}
	return null;
}
```

return 안, jsx내에서 if문을 사용하는 건 불가능하다

<div> if (){} </div> 이거 불가능

따라서 return + jsx 전체를 리턴해주는 if문을 작성

### 2. 삼항 연산자

```js
function Component() {
	return <div>{1 === 1 ? <p>참이면 보여줄 HTML</p> : null}</div>;
}
```

중첩 사용도 가능

```js
function Component() {
	return <div>{1 === 1 ? <p>참이면 보여줄 HTML</p> : 2 === 2 ? <p>안녕</p> : <p>반갑</p>}</div>;
}
```

### 3. && 연산자로 if 역할 대신하기

> &&연산자
>
> 왼쪽 오른쪽 둘다 true 면 => 전체 true

```js
true && false; //false
true && true; //true
```

```js
true && '안녕'; //안녕
false && '안녕'; //false
```

```js
function Component() {
	return <div>{1 === 1 && <p>참이면 보여줄 HTML</p>}</div>;
}
```

### 4. switch / case 조건문

- if else

  ```js
  function reducer(state, 액션) {
  	if (액션.type === '수량증가') {
  		return 수량증가된state;
  	} else if (액션.type === '수량감소') {
  		return 수량감소된state;
  	} else {
  		return state;
  	}
  }
  ```

- switch

  ```js
  function reducer(state, 액션){

  switch (액션.type) {
    case '수량증가' :
      return 수량증가된state;
    case '수량감소' :
      return 수량감소된state;
    default :
      return state
  }
  ```

}

### 5. 오브젝트 자료형을 응용한 enum

쇼핑몰에서 상품 설명 부분을 탭으로 만든다고 하면

탭 안에는 경우에 따라 상품정보/ 배송정보/ 환불약관을 보여준다

state가 info면 <p>상품정보</p>

state가 shipping이면 <p>배송정보</p>

```js
function Component() {
	var 현재상태 = 'info';
	return (
		<div>
			{
				{
					info: <p>상품정보</p>,
					shipping: <p>배송관련</p>,
					refund: <p>환불약관</p>,
				}[현재상태]
			}
		</div>
	);
}
```

key값이 '현재상태'인 자료를 선택

위에 var의 값에 넣어준 항목의 값이 보여지는 것!

- 깔끔하게 정리

  ```js
  var 탭UI = {
  	info: <p>상품정보</p>,
  	shipping: <p>배송관련</p>,
  	refund: <p>환불약관</p>,
  };

  function Component() {
  	var 현재상태 = 'info';
  	return <div>{탭UI[현재상태]}</div>;
  }
  ```

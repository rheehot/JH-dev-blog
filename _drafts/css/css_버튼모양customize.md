# css 버튼 커스텀 스타일 적용하기

버튼의 background color 와 border 그리고 padding 을 조절해주면
기본적인 스타일은 사라진다

## 버튼 스타일 커스텀

```html
<html>
	<head>
		<style>
			button {
				background: rgba(0, 0, 0, 0); // 버튼 배경 색
				border: 1px solid skyblue; // 테두리
				color: white; // 글자색
				padding: 5px;
				border-radius: 1px 2px 3px 4px; // 모서리 둥글게 (right-top 부터 시계방향)

				// border-top-left-radius: 1px 이렇게 써도 됨
			}
		</style>
	</head>
	<body>
		<button>버튼</button>
	</body>
</html>
```

## hover 했을 때 스타일

```css
button:hover {
	cursor: pointer; // 커서 모양 포인터
	background: skyblue;
	color: white;
}
```

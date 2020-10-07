# css 박스 그림자 효과(feat. box-shadow)

box-shadow: none | h-shadow v-shadow blur spread color | insert

- h-shadow: 수평 그림자 위치(필수)

- v-shadow: 수직 그림자 위치(필수)

- blur: 그림자의 흐림정도(선택)

- spread: 그림자가 드리워지는 정도(선택)

```css
.box {
	box-shadow: 10px, 10px, 10px 20 grey;
}
```

- 접두어 버전과 함께 쓸경우 표준 속성을 맨 아래에 씀

  ```css
  .box {
  	-moz-box-shadow: 10px 10px 10px 20 grey;
  	-webkit-box-shadow: 10px 10px 10px 20 grey;
  	box-shadow: 10px, 10px, 10px 20 grey;
  }
  ```

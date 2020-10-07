https://poiemaweb.com/css3-selector

# css 선택자

## 종류

- 전체 선택자(\*)
  margin 이나 padding 값의 초기화나 기본값을 정해둘 때 사용
  하지만 모든 요소를 읽어햐 하기 때문에 페이지 로딩 속도가 느림 -> 자주 사용X

  ```css
  * {
  	margin: 0;
  	text-decoration: none;
  }
  ```

- 태그 선택자(tagName)

  ```css
  p {
  	background: pink;
  	color: white;
  }
  ```

- 클래스 선택자(.className)

  ```css
  .class1 {
  	background: purple;
  	color: white;
  }
  div.class2 {
  	//div태그 중에서 클래스네임이 class2인 요소
  	background: blue;
  	color: white;
  }
  ```

- ID 선택자 (#idName)

  ```css
  #id1 {
  	background: yellow;
  	color: white;
  }
  ```

### Q 클래스 선택자 vs ID 선택자

1. 한 페이지 내에서 여러 번 반복될 필요가 있는 스타일은 클래스 선택자

   단 한번 유일하게 적용될 스타일은 ID 선택자

2. 클래스 선택자는 글자색이나 글자 굵기 등 나중에 다른 곳에도 적용할 수 있는 스타일을 지정
   ID 선택자는 웹 문서 안에서 요소의 배치 방법을 지정할 때 자주 사용

3. 클래스 속성은 속성값을 두개 이상 가질 수 있다. 따라서 여러 종류의 스타일 규칙을 적용할 수 있다.

4. ID 선택자 > 클래스 선택자 : 우선으로 적용되야 할 스타일은 ID선택자를 사용

## 복합 선택자

복합 선택자는 두 개 이상의 선택자 요소가 모인 선택자입니다.

- 하위 선택자
  부모요소에 포함된 '모든' 하위 요소에 스타일 적용
  ```css
  section ul {
  	border: 1px dotted black;
  }
  ```
- 자식 선택자
  부모의 바로 아래 자식 요소에만 적용

  ```css
  section > ul {
  	border: 1px solid pink;
  }
  ```

- 인접 형제 선택자 (E+F)
  E요소를 뒤따르는 F요소를 선택 (그 사이에 다른 요소가 존재하면 선택하지 않음)

  ```css
  h1 + ul {
  	// h1을 뒤따르는 ul를 선택
  	background: yellowgreen;
  	color: green;
  }

  -----
  <section>
    <ul></ul>
    <h1></h1>
    <ul></ul> //선택
    <ul></ul>
  </section>
  ```

- 일반 형제 선택자 (E~F)
  E요소가 앞에 존재하면 F를 선택 (E가 F보다 먼저 등장하지 않으면 선택하지 않음)

  ```css
  h1 ~ ul {
  	background: darkgreen;
  	color: white;
  }

  -----
  <section>
    <ul></ul>
    <h1></h1>
    <ul></ul> //선택
    <ul></ul> //선택
  </section>
  ```

- 속성 선택자

  ```
  E[attr] : 'attr'속성이 포함된 요소 E를 선택
  E[attr="val"] : 'attr'속성의 값이 정확하게 'val'과 일치하는 요소 E 선택
  E[attr~="val"] : 'attr'속성의 값에'val'이 포함되는 요소를 선택 (공백으로 분리된 값이 일치해야 함)
  E[attr^='val] : 'attr'속성의 값이 'val'으로 시작하는 요소
  E[attr$="val"] : 'attr'속성의 값이 'val'으로 끝나는 요소
  E[attr*='val'] : 'attr'속성의 값에 'val'이 포함되는 요소
  E[attr|='val'] : 'attr'속성의 값이 정확하기 'val'이거나 'val-'으로 시작되는 요소
  ```

  - E[attr^='val] 의 경우, 웹 문서에서 외부로 연결되는 링크가 있을 경우 'http://'로 시작하는 지 확인하기 위해
    이 선택자를 쓸 수 있습니다. 반대로 E[attr$='val']형식의 경우, 어떤 파일이 링크될 경우, 그 파일의 확장자를 확인하기 위해 쓸 수 있다

--아직 정리 덜 함..
http://www.nextree.co.kr/p8468/

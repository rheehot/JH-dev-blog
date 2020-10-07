# 검색필터 드롭다운

https://www.w3schools.com/howto/howto_js_filter_dropdown.asp

##

1. 드롭박스를 나타나게 하는 버튼 + 그 아래 내용 같은 계층에 위치(display none)

2. 찾기는 --> input type text 로 구성

3. 나머지는 a태그로 구성

```html
<div class="dropdown">
	<button onclick="myFunction()" class="dropbtn">Dropdown</button>
	<div id="myDropdown" class="dropdown-content">
		<input type="text" placeholder="Search.." id="myInput" onkeyup="filterFunction()" />
		<a href="#about">About</a>
		<a href="#base">Base</a>
		<a href="#blog">Blog</a>
		<a href="#contact">Contact</a>
		<a href="#custom">Custom</a>
		<a href="#support">Support</a>
		<a href="#tools">Tools</a>
	</div>
</div>
```

4.

```css
.show {
	display: block;
}
```

```js
function myFunction() {
	document.getElementById('myDropdown').classList.toggle('show');
}

function filterFunction() {
	var input, filter, ul, li, a, i;
	input = document.getElementById('myInput');
	filter = input.value.toUpperCase();
	div = document.getElementById('myDropdown');
	a = div.getElementsByTagName('a');
	for (i = 0; i < a.length; i++) {
		txtValue = a[i].textContent || a[i].innerText;
		if (txtValue.toUpperCase().indexOf(filter) > -1) {
			a[i].style.display = '';
		} else {
			a[i].style.display = 'none';
		}
	}
}
```

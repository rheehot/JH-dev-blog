# scss 조건문 (feat. @if, @else if, @else)

```scss
@if condition1 {
  A
} @else if condition2 {
  B
} @else {
  C
​}
```

```scss
$jb-type: jb-blue;
p {
	@if $jb-type == jb-red {
		color: red;
	} @else if $jb-type == jb-blue {
		color: blue;
	} @else {
		color: black;
	}
}
```

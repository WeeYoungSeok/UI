# CSS

- CSS(**C**ascading **S**tyle **S**heets)

  > 문서의 스타일을 지정해주는 언어
  >
  > ** 문서(doucument) : markup language (html, xml, ...)**

```html
<li><font color="red">HTML</font></li>
<li><font color="red">CSS</font></li>

<!-- <li> : 정보 태그
	 <font> : 스타일 (시각적인 효과) 태그
	 => 정보와 디자인이 혼합되어 있어서, 보기에 좋지 않다. -->
```

------

### 표현 방법

- 인라인 : tag 안에서

  > `<태그 style="속성='값';">`

- 내부 : head 안에서

  > `<style>`...`</style>`

- 외부 : head 안에서 .css 파일 연결

  > `<link href="파일.css" rel="stylesheet" type="text/css">`
  >
  > **순서 : 절차식 (마지막에 선언된 스타일이 우선순위를 가진다.)**



### 선택자

- selector : 스타일을 적용시킬 범위를 선택하기 위한 표현석

  > 타입, id, class, 전체, 자식, 인접, 속성, 가상 class, 종속, 하위, 그룹 선택자가 있다.



- 타입 선택자

  > 태그 이름을 지정하여 선언
  >
  > 동일한 속성에 대한 여러 요소를 콤마(,)로 구분하여 선언 가능

```html
<style type="text/css">
    h1{font-size:10px;}
    h1,h2,h3{color:blue;}
    ul{margin: 0px;}
</style>
<!-- 표현 방법중 내부 -->
```

```css
h1{
    font-size: 10px;
}
h1,h2,h3{
    color: blue;
}
ul{
    margin: 0px;
}
/* 표현 방법중 외부 */
```



- id 선택자

  > 요소에 id를 지정하고, style에서 지정된 id값으로 사용
  >
  > #으로 구분한다.
  >
  > '유일한 하나'인 경우에 사용하는 것이 좋다.

```html
<style type="text/css">
    #header{margin: 0px}
</style>
...
<div id="header"></div>
```

```css
#header{
    margin: 0px
}
```



- class 선택자

  > 요소에 class를 지정하고, style에서 지정된 class 값으로 사용
  >
  > .(dot)으로 구분한다.
  >
  > 한번에 여러 개를 바꿀 때 사용하는 것이 좋다.

```html
<style type="text/css">
    .content{font-size: 10px;}
</style>
...
<div class="content">1</div>
<div class="content">2</div>
```

```css
.content{
    font-size: 10px;
}
```



- 전체 선택자

  > *을 사용한다. (자주 사용하진 않음)

```html
<style type="text/css">
    *{font-size: 10px;}
</style>
```

```css
*{
    font-size: 10px;
}
```



- 자식 선택자

  > 부모/자식 관계에서 자식 요소를 지정한다

```html
<style type="text/css">
    div > p{font-size: 10px; color: blue;}
    p > span{color: red;}
</style>
...
<div><p>자식선택자</p></div>
<p><span>나도 자식인가</span></p>
<!-- A > B A가 부모 B가 자식
	 p는 블록 요소 span은 인라인 요소 자식이 될수 있음. -->
```

```css
div > p{
    font-size: 10px; color: blue;
}
    p > span{
        color: red;
}
```





- 인접 선택자

  > 지정한 요소 바로 다음에 나오는 요소를 선택한다.

```html
<style type="text/css">
    h1+span{color: red;}
</style>
...
<h1>인접<span>했나요?</span></h1>
<span>인접했나요!</span>
```
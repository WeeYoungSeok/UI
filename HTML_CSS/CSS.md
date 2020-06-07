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



- 속성 선택자

  > 속성이 정의된 태그만 선택

```html
<sytle type="text/css">
	h1[class]{color:blue};
</sytle>

<h1 class="abc">속성(class)있음</h1>
<h1>속성(class)없음</h1>
```

- 종류

  > [attribute] : attribute라는 속성을 가지고 있는 요소들을 선택
  >
  > [attribute=value] : 속성갑소가 일치하는 요소들을 선택
  >
  > [attribute~=value] : 속성값과 일치하는 요소들을 선택, 
  >
  > 공백으로 구분하여 포함된 속성값도 선택
  >
  > [attribute|=value] : 속성값으로 시작하는 요소들을 선택,
  >
  > 하이폰(-)으로 구분하여 포함된 속성값도 선택
  >
  > [attribute^=value] : 속성값으로 시작하는 요소들을 선택
  >
  > [attribute$=value] : 속성값으로 끝나는 요소들을 선택
  >
  > [attribute*=value] : 속성값을 포함하고 있으면 선택 (위치 상관 없음)



- 가상 클래스 선택자

  > 요소의 상태에 따라 선택자 지정
  >
  > 상태가 html 문서에 표현되는 것은 아님
  >
  > css에서만 구별

```html
<style type="text/css">
    a:link{color:blue; text-decoration:none;} /* 방문하지 않은 링크 */
    a:visited{color:red; text-decoration: none;} /* 방문했던 링크 */
    a:hover,a:active{color:yellow; text-decoration:underline;} /*마우스 오버, 클리시 */
</style>
```



- 종속 선택자

  > 타입, id, class 선택자가 결합된 상태

```html
<style type="text/css">
    p.sel a{font-size: 10px;}
    div #mul{color:red;}
</style>
```



- 하위 선택자

  > 특정 요소 하위의 요소를 지정할 때 사용
  >
  > 공백으로 작성

```html
<style type="text/css">
    h1 span{font-size: 10px;}
</style>

<h1><span>abc</span>abc</h1>
```



- 그룹 선택자

  > 여러 오소에 각각 같은 속성 적용
  >
  > ,(콤마)로 구분

```html
<style type="text/css">
    p, li, a{margin: 0px; color: blue;}
</style>
<p>abc</p>
<ul>
    <li>1</li>
    <li>2</li>
    <li>3</li>
</ul>
<a href="#">abc</a>
```



### 선택자 우선순위

- 스타일 선언은 위에서 아래로 순차적으로 실행되면서 마지막에 선언된 스타일이 우선순위임

```html
<style type="text/css">
    .test{color: red;}
    .test{color: blue;}
    .test{color: yellow;}
</style>

<p class="test">abc</p>
```

**class test의 최종 폰트 색은 yellow**



- *특정 요소에 중복 선언할 경우

```html
<style type="text/css">
    .test02{color: red;}
    p{color: blue;}
    #test01{color: yellow;}
</style>

<p id="test01" class="test02" style="color:red;">우선순위</p>
```

**inline > id > class > type**



- *강제 우선순위 선언

```html
<style type="text/css">
    .test02{color: red;}
    p{color: blue; !important;}
    #test01{color: yellow;}
</style>

<p id="test01" class="test02" style="color:red;">우선순위</p>
```

**!important > inline > id > class > type**



- 서체

  > 글자와 관련된 스타일을 지정할 수 있는 속성
  >
  > > font-family : 글꼴 지정
  > >
  > > font-size : 크기 지정
  > >
  > > font-weight : 굵기 지정
  > >
  > > font-style : 글씨체 지정
  > >
  > > font-variant : 소문자 -> 대문자 변환 (일반 대문자보다 작다)
  > >
  > > Lint-height : 줄 간격 지정
  > >
  > > font : 위 속성을 한 줄에 모두 지정 (font-size/font-family 생략 불가)



- 문단

  > paragraph : 문단을 중심으로 정렬, 들여쓰기 등을 지정
  >
  > > text-align : 글자의 정렬 기준 지정 (justify : 양쪽정렬)
  > >
  > > vertical-align : 이미지나 폼 요소를 세로 정렬
  > >
  > > text-indent : 들여쓰기
  > >
  > > text-transform : 대소문자 변경 (capitalize : 첫 글자만 대문자)
  > >
  > > text-decoration : 밑줄 등 (밑줄, 가운데 줄, 윗줄, 밑줄 제거)
  > >
  > > letter-spacing : 글자와 글자간의 간격



- 배경

  > background
  >
  > > background-color : 배경 색 지정
  > >
  > > background-repeat : 배경 이미지 지정
  > >
  > > background-position : 배경 이미지 반복 지정
  > >
  > > background-attachment : 배경 이미지의 고정 여부
  > >
  > > background : 관련 속성을 한 줄로 표기



- 상자

  > width, height : px, &, em 등으로 수치 표기

![](https://k.kakaocdn.net/dn/c6OzGD/btqEGUfZY2b/JYYh8T28qlZoX8JW26GPw0/img.png)

- 상자

  > margin (바깥여백), border (테두리), padding (안쪽여백)

![](https://k.kakaocdn.net/dn/s2Nr1/btqEFDUgPvn/NmK95oJKqXhzD478vB48m1/img.png)

- 상자

  > margin 병합 : 세로 방향 margin을 지정한 두 개의 서로 다른 요소가 수직 방향으로 접해있을 때 두 요소 사이의 margin 간격은 큰 쪽으로 병합

![](https://k.kakaocdn.net/dn/bYEUXV/btqEHwZ2zWJ/jJbJNIrVhiAx85eE2tS9z1/img.png)

- 상자

  > margin을 이용한 중앙 정렬
  >
  > 박스의 좌우 속성값을 auto로 지정해서 중앙에 위치.
  >
  > (정렬하려는 박스의 width를 반드시 지정)

![](https://k.kakaocdn.net/dn/evHzZL/btqEHycu49N/beKKUAIzMp6RrCPLHuEB01/img.png)



- layout : 블록들의 위치를 나열

  > float : 요소를 블록형태로, 특정 방향으로 정렬
  >
  > clear : float을 해제할 때 사용
  >
  > **이전 요소의 float값을 상속받아, 같은 방향으로 정렬되는 현상 방지**
  >
  > display : 요소의 성격을 바꿔주는 속성 (인라인 요소 <-> 블록 요소)
  >
  > overflow : 박스 안의 내용이 박스보다 클 경우, 넘치는 부분을 처리
  >
  > **부모 사이즈가 지정되어 있어야 사용 가능**
  >
  > position : 블록박스의 위치를 지정하는 속성 (겹치게 배열 가능)



- border

  > border-radius : 박사의 태두리 선을 둥굴게
  >
  > box-shadow : 박스의 그림자 지정
  >
  > border-image : 특정 이미지를 테두리의 배경으로 지정



- background

  > gradient : 여러 색을 원형이나 선형으로 칠해주는 효과
  >
  > background-size : 배경 이미지 크기 조정
  >
  > background-origin : 배경 이미지 테두리 맞춤
  >
  > multi-background : 배경 이미지 여러 개 지정
  >
  > background-clip : origin과 비슷



- text

  > text-shadow : 택스트에 그림자 지정
  >
  > word-wrap : 자동 줄바꿈
  >
  > font-face : 웹폰트 설정



- 2d transform

  > rotate : 회전
  >
  > scale : 확대/축소
  >
  > translate : 이동
  >
  > skew : 찌그러뜨리기



- transitions

  >  background, color, height, width, transformation 등의 속성들에 애니메이션 적용

- animation

  > 박스의 크기, 위치, 색상 등의 값을 여러 단계로 나눠 실행 (애니메이션 효과)

- 다단 편집

  > multi coumn 지원

- 사용자 환경

  > box-sizing : border가 박스 크기에 포함/미포함
  >
  > resize : 박스의 크기 조절
  >
  > outline : border를 감싸는 테두리
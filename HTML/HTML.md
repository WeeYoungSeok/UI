# HTML

- HTML : **H**yper**T**ext **M**arkup **L**anguage

  > 온라인 상의 문서(page)를 만들기 위한 `구조화` 된 언어.

```html
<!DOCTYPE html>					<!-- 문서의 타입을 정의 -->
<!-- html5 version -->
<html>							<!-- 이 문서는 html이다 -->
    <head>						<!-- 문서를 정의 -->
        <titl>Hello, World</titl>
    </head>
    <body>						<!-- 문서의 내용 -->
        <p>Hello, World! Hello, Web!</p>
    </body>
</html>
```



- HTML 요소(elemanet, tag)의 구성

  > `<tag> </tag>`- `<div> </div>` 
  >
  > `<tag 속성 = '값'> </tag>` - `<div align='center'> </div>`
  >
  > ``<tag 속송 = '값'> 문자 </tag>` - `<p style='color:red;'> Hello, World! </p>`



- 문서를 정의(`<head>`)하는 기본 태그

  > `<meta>` : 문서의 기본 정보 등을 정의
  >
  > `<title>` : 문서의 제목을 정의
  >
  > `<script>` : javascript 등을 정의
  >
  > `<style>` : css 등을 정의
  >
  > `<link>` : 외부 문서를 연결할 때 정의

  

- DTD(**D**ocument **T**ype **D**efinition) 선언

  > strict : 선언된 html 버전의 문법과 구조를 정확하게 사용
  >
  > transitional : 선언된 html 버전 이외의 문법과 구조를 허용
  >
  > frameset : transitional + frame 지원 (사실상 transitional과 동일)

  

- DTD 해석

```html
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Frameset//EN"
"http://www.w3.org/TR/html4/frameset.dtd">
<!-- 이 문서는 html로 작성하고, 국제공용문서이며,
W3C기관에 문서형식에 의해 HTML4.01을 Frameset방ㅎ식의 영어로 출력하고,
참조할 DTD문서는 http://www.w3.org/TR/html4/frameset.dtd 이다. -->
```



### 문법

- HTML 문법

  > 요소를 정확하게 매칭
  >
  > 요소, 속성 이름은 소문자
  >
  > 요소는 항상 닫아야 한다. (일부 단일 태그 존재 ex <img .../>)
  >
  > 특수문자를 쓸 때는 Entity Name(code)으로 사용



- 블록 요소, 인라인 요소

| 유    형    | 특     징                                                    |
| ----------- | ------------------------------------------------------------ |
| 블록 요소   | 줄 바꿈<br />블록 요소 안에 텍스트와 인라인 요소 포함 가능<br />블록 요소 안에 블록 요소 포함 가능 (일부 불가) |
| 인라인 요소 | 줄 바꿈x<br />인라인 요소 안에 텍스트와 인라인 요소 포함 가능<br />인라인 요소 안에 블록 요소 포함 불가 |

***인라인 요소 안에 블록 요소가 포함 불가이지만 사용은 됨, 하지만 안쓰는 방식을 지양하자***



- 제목태그

  > `<h1> ~ <h6>` (총 6개)
  >
  > 문서 내부의 컨텐츠 제목을 정의
  >
  > 순서에 맞게 작성
  >
  > css로 임의의 크기 지정 가능
  >
  > h1은 한 문서에 한번만 지정하는 것을 권장 



- 단락(paragraph)

  > `<p>`
  >
  > > 블록 요소 (다른 블록 요소 포함 불가)
  >
  > `<br/>`
  >
  > > 문단 간격 정의 태그, 개행요소, 빈요소(종료 태그 x) (html5 버전부터 종료 태그 없음)



- 주소

  > `<address>`
  >
  > > 연락처 정보 나타내는 요소
  > >
  > > 블록 요소 (다른 블록 요소 포함 불가) 단, DTD가 ***transitional*** 인 경우 포함 가능



- 구분선 (Horizontal line)

  > `<hr>`
  >
  > > 블록 요소이지만, 빈 요소이기에 종료 태그 없다. (html5 버전부터 종료 태그 없음)
  > >
  > > css 대신 내용 구분할 때 주로 사용



- 인용문 (Quotation)

  > `<blockquote>`
  >
  > > 다른 사이트에서 인용한 일부르 지정
  > >
  > > 블록 요소인 p요소 사용
  > >
  > > cite 속성 : 인용문의 출처, cite 요소 : 작품의 제목
  >
  > `<p>`
  >
  > > 짧은 인용문 지정
  > >
  > > 텍스트나 인라인 요소 포함



- 텍스트 표현 요소

  > `<b>` : 텍스트 진하게
  >
  > `<strong>` : 텍스트 진하게
  >
  > `<em>` : 텍스트 기울임
  >
  > `<i>` : 텍스트 기울임
  >
  > `<small>` : 작은 텍스트 표시, 코멘트 등
  >
  > `<sub>` : 아래 첨자
  >
  > `<sup>` : 윗 첨자
  >
  > `<ins>` : 내용 추가
  >
  > `<del> ` : 내용 삭제

**텍스트 진하게, 기울임같은 경우는 기본적으로 쓰이는 것이 `<b>, <i>`이다.**

**`<strong>, <em>`은 웹 접근성 표현 요소이다.**

*웹 접근성이란?*

> 장애인이나 고령자는 물론 어떤 사용자들도 웹사이트에서 제공하는 정보를 비장애인과 동등하게 접근하고 활용할 수 있도록 하자는 개념이다.
>
> ex) 홈페이지에서 소리로 읽어주는 기능이 있는 경우 웹 접근성 표현 요소를 사용하면 소리로 홈페이지에서 읽어줄때도 강조하여서 읽어준다.



- 이미지 (image) - `<img alt="" src=""/>`

  > 주요 속성
  >
  > > alt : 이미지를 설명하는 내용 지정, 이미지가 보이지 않을 경우, 이미지 설명 텍스트
  > >
  > > width : 이미지의 가로 크기 지정
  > >
  > > height : 이미지의 세로 크기 지정
  > >
  > > src : 이미지 경로 지정



- 링크

  > `<a>`
  >
  > > 텍스트나 이미지 등을 통해 다른 페이지로 정보 연결
  > >
  > > 인라인 요소 (인라인 요소화 텍스트를 포함)
  > >
  > > 주요속성
  > >
  > > href : 링크의 주소 지정
  > >
  > > title : 링크의 설명 표시
  > >
  > > target : 링크된 문서를 어떤 창에서 오픈할 것인지 지정



- 기본 목록 구성

  > 주로 메뉴 작성시 사용
  >
  > > `<ui>` : 비 순차적 목록 나열
  > >
  > > `<ol>` : 순차적 목록 나열
  > >
  > > `<li>` : 목록의 내용



- 테이블

  > `<table>`
  >
  > 문서에 표를 작성할 때 사용
  >
  > 주요 속성
  >
  > > rowspan : 수직방향으로 셀 병합
  > >
  > > colspan : 수평방향으로 셀 병합



- 테이블 주요 구성 태그

  > `<tr>`: 행 정의, th와 td만 자식 요소로 포함
  >
  > `<th>` : 제목 셀 정의
  >
  > `<td>` : 데이터 셀 정의
  >
  > `<thead>` : 테이블의 머리글
  >
  > `<tbody>` : 테이블의 본문
  >
  > `<tfoot>` : 테이블의 바닥글
  >
  > `<caption>` : 테이블 제목
  >
  > `<col>` : 테이블 열 정의
  >
  > `<colgroup>` : 테이블의 열 그룹화



- `<form>`

  > 폼의 최상위 요소, 퐁을 구성할때 정의
  >
  > 주요 속성 및 태그
  >
  > > action : 폼 서식에 작성한 값들을 처리할 서버 프로그램 주소
  > >
  > > method : 작성된 값들의 전송 방식 설정 (get, post)
  > >
  > > `<fieldset>` : 여러 폼 요소들의 그룹화 범위 지정
  > >
  > > `<legend>` : 그룹화 제목 표시
  > >
  > > `<input>` : 폼 안에 기본적인 컨트롤 생성
  > >
  > > `<textarea>` : 여러줄로 된 텍스트 필드 생성
  > >
  > > `<select>`,`<option>` : 선택 목록 정의, 목록 표시
  > >
  > > `<button>` : `<input type="button">`과 기능적으로 같지만, 보다 유연하게 표현 가능



- `<input type="">` 요소의 type 값

  > text : 일반 텍스트
  >
  > password : 비밀번호 (*로 표시)
  >
  > checkbox : 체크박스 (중복 가능)
  >
  > radio : 라디오버튼 (중복 불가)
  >
  > submit : 전송 버튼
  >
  > reset : 폼 안의 입력요소 값 초기화
  >
  > button : 기본 버튼
  >
  > image : 이미지 버튼
  >
  > file : 파일 선택
  >
  > hidden : 화면에 표시되지 않음 (기능은 정상 작동)

- `<input type="">` 요소의 속성

  > name : 컨트롤의 이름 설정 (서버와의 데이터처리 작업 시, 반드시 필요)
  >
  > value : 컨트롤의 값
  >
  > size : 컨트롤의 가로 크기
  >
  > maxlength : 최대 입력 문자수 지정
  >
  > checked : 체크박스, 라디오버튼의 초기 선택 지정
  >
  > disabled : 포커스, 선택, 변경 불가
  >
  > readonly : 입력내용 변경 불가, 데이터 전송 가능



- `<textarea>` 속성

  > name, disabled, readonly : input 요소 속성과 동일
  >
  > rows : 표시 줄 수 지정 (브라우저에 보이는 줄 수 의미)
  >
  > cols : 표시 폭 지정 (브라우저의 설정에 따라 차이가 있을 수 있음)



- grouping

  > 여러 요소를 그룹화, css 적용시 많이 사용
  >
  > > `<div>` : 블록 요소
  > >
  > > `<span>` : 인라인 요소



### html5

- 새로운 구조

  > `<hgroup>` : 제목과 부제목을 묶어주는 요소, 최상위 제목만 outline 된다
  >
  > `<section>` : 의미가 같은 내용들을 그룹화   
  >
  > ​      **`<h>`, `<p>`, `<section>`, `<article>`을 묶을 때나, 독립된 영역을 만들때도 사용**
  >
  > `<header>` : 문서의 머릿말
  >
  > `<footer>` : 문서의 꼬릿말
  >
  > `<nav>` : 메인 네비게이션
  >
  > `<article>` : 문서에서 독립적인 컨텐츠
  >
  > `<aside>` : 사이드바 (메인 컨텐츠와 분리된, 독립적 요소)

![](https://k.kakaocdn.net/dn/bdZoRi/btqEBeGkNgs/3uMgKt3cZ0dK5XUlExPno0/img.png)

- 추가된 요소

  > `<figure>` : 삽화, 다이어그램, 사진 코드목록 등에 설명을 달아줌
  >
  > `<mark>` : 부분 강조
  >
  > `<time>` : 날짜와 시간을 기계가 이해할 수 있는 형태로 (data type으로)
  >
  > `<details>` : 접기/펼치기 기능 (summary : details의 제목)
  >
  > `<progress>` : 다운로드 진행상황
  >
  > `<meter>` : 현재 진행 상황



- `<form>`에 추가된 속성

  > `<input type="">` : search, email, url, tel, number, range, date, datetime

  ​										datetime-local, month, week, time, color

  > > required : 유효성 검사
  > >
  > > placeholder : 입력 형식 힌트
  > >
  > > autocomplete : 자동완성
  > >
  > > lis : 자동완성과 비슷한 기능 (미리 만들어놓는 리스트 보여줌)
  > >
  > > autofocus : 커서 자동 이동
  > >
  > > pattern : 정규 표현식 방법으로 유효성 검사
  > >
  > > multiple : 다중 파일 선택


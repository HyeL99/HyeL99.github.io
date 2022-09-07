---
title: HTML 공간 분할
author: HyeL
date: 2022-09-07 10:15:00 +0900
categories: [Coding Diary, HTML/CSS]
tags: [html, 코딩일지]
---

## 블록과 인라인
HTML의 모든 요소는 해당 요소가 웹 브라우저에 어떻게 보이는가를 결정짓는 display 속성을 가진다.<br>
display 속성은 주로 4가지 속성값이 쓰이는데, 태그마다 기본값이 다르다.

- `none`: 보이지 않음, 영역도 차지하지 않음
- `block`: 블록 박스, 가로 영역을 모두 채우고 크기를 지정할 수 있으며, 다음 태그는 아랫줄에 표시됨
- `inline`: 인라인 박스, 줄바꿈 되지 않고, 크기를 지정할 수 없음
- `inline-block`: block과 inline의 중간 형태, 줄바꿈 되지 않고 크기를 지정할 수 있음

이중 레이아웃에 주로 쓰이는 속성값은 아래 두가지 값이다.

- 블록(block)
- 인라인(inline)

- ### 블록(block) 타입의 요소

    display 속성값이 블록(block)인 요소는 언제나 새로운 라인(line)에서 시작하며, 해당 라인의 모든 너비를 차지한다.<br>
    <div>요소는 다른 HTML 요소들을 하나로 묶는 데 자주 사용되는 대표적인 블록(block) 요소이다.<br>
    <div>요소는 주로 여러 요소들의 스타일을 한 번에 적용하기 위해 사용된다.

- ### 인라인(inline) 타입의 요소

    display 속성값이 인라인(inline)인 요소는 새로운 라인(line)에서 시작하지 않는다.
    또한, 요소의 너비도 해당 라인 전체가 아닌 해당 HTML 요소의 내용(content)만큼만 차지한다.
    <span>요소는 텍스트(text)의 특정 부분을 묶는 데 자주 사용되는 인라인(inline) 요소이다.
    <span>요소는 주로 텍스트의 특정 부분에 따로 스타일을 적용하기 위해 사용된다.

    ```html
    <div style="background-color:lightgrey; color:green; text-align:center">
        <h4>div요소를 이용한 스타일 적용</h4>
        <p>div요소로 여러 요소들을 묶은 뒤, style 속성과 클래스 등을 이용하여
        한 번에 스타일을 적용할 수 있다.</p>
        <p>
            이렇게
            <span style="border: 3px solid red">span요소로 텍스트의 일부분</span>
            만을 따로 묶은 후에 스타일을 적용할 수 있다.
        </p>
    </div>
    ```

    <div style="background:#eee; padding: 20px; box-sizing: border-box; border-radius: 10px; color: black;">
        <strong style="display: block; padding-bottom: 20px;">▶ 실행결과</strong>
        <div style="background-color:lightgrey; color:green; text-align:center">
            <h4 style="margin:0;">div요소를 이용한 스타일 적용</h4>
            <p>div요소로 여러 요소들을 묶은 뒤, style 속성과 클래스 등을 이용하여
            한 번에 스타일을 적용할 수 있다.</p>
        </div>
        <p>
            이렇게
            <span style="border: 3px solid red">span요소로 텍스트의 일부분</span>
            만을 따로 묶은 후에 스타일을 적용할 수 있다.
        </p>
    </div>

## ifram 요소
    iframe이란 내부 프레임(inline frame)이라는 의미로,
    iframe요소를 이용하면 어떠한 제한 없이 하나의 HTML 문서 내에서 다른 HTML 문서를 보여줄 수 있으며 동영상도 보여줄 수 있다.

    ```
    문법
    <iframe src="삽입할페이지주소"></iframe>
    ```

    iframe요소는 종료 태그가 존재하며, 명시된 크기로 창의 사이즈가 고정된다.

    ```html
	<iframe src="/css/intro" style="width:100%; height:100px">
    </iframe>
    ```

    <div style="background:#eee; padding: 20px; box-sizing: border-box; border-radius: 10px; color: black;">
        <strong style="display: block; padding-bottom: 20px;">▶ 실행결과</strong>
        <div id="header" style="background-color:lightgrey; height:100px; text-align:center; line-height:100px;">
            <p>HEADER 영역</p>
        </div>
        <div id="nav" style="background-color:#339999; width:30%; float:left; text-align:center; line-height:240px; padding:30px;">
            <p style="margin:0; color: #fff;">NAV 영역</p>
        </div>
        <div id="section" style="background-color:crimson; width:70%; float:left; padding:30px; line-height:80px;">
            <p style="margin:0; color: #fff;">SECTION 영역<br>SECTION 영역<br>SECTION 영역</p>
        </div>
        <div id="footer" style="background-color:#FFCC00; height:100px; clear:both; text-align:center; line-height:100px;">
            <p>FOOTER 영역</p>
        </div>
    </div>


## 레이아웃(Layout)

레이아웃(Layout)이란  제한된 공간 안에 효과적으로 배열하는 일을 의미한다.<br>
HTML에서는 다음과 같은 방법으로 레이아웃을 작성할 수 있다.

1. div요소를 이용한 레이아웃
2. HTML5 레이아웃
3. table 요소를 이용한 레이아웃

- ### div요소를 이용한 레이아웃

    div 요소는 CSS 스타일을 손쉽게 적용할 수 있으므로, 레이아웃을 작성하는데 자주 사용된다.

    ```html
	<div id="header">
		<p>HEADER 영역</p>
	</div>
	<div id="nav">
		<h2>NAV 영역</h2>
	</div>
	<div id="section">
		<p>SECTION 영역</p>
	</div>
	<div id="footer">
		<h2>FOOTER 영역</h2>
	</div>
    ```

    <div style="background:#eee; padding: 20px; box-sizing: border-box; border-radius: 10px; color: black;">
        <strong style="display: block; padding-bottom: 20px;">▶ 실행결과</strong>
        <div id="header" style="background-color:lightgrey; height:100px; text-align:center; line-height:100px;">
            <p>HEADER 영역</p>
        </div>
        <div id="nav" style="background-color:#339999; width:30%; float:left; text-align:center; line-height:240px; padding:30px;">
            <p style="margin:0; color: #fff;">NAV 영역</p>
        </div>
        <div id="section" style="background-color:crimson; width:70%; float:left; padding:30px; line-height:80px;">
            <p style="margin:0; color: #fff;">SECTION 영역<br>SECTION 영역<br>SECTION 영역</p>
        </div>
        <div id="footer" style="background-color:#FFCC00; height:100px; clear:both; text-align:center; line-height:100px;">
            <p>FOOTER 영역</p>
        </div>
    </div>

- ### HTML5 레이아웃

    HTML5에서는 웹 페이지의 레이아웃만을 위한 별도의 시멘틱 태그들을 제공한다.
    ![enter image description here](http://www.tcpschool.com/lectures/img_html_html5_layout.png)

    <table style="width:100%;">
        <thead>
            <tr class="bg">
                <th>의미 요소</th>
                <th>설명</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>&lt;header&gt;</td>
                <td>HTML 문서나 섹션(section) 부분에 대한 헤더(header)를 정의함.</td>
            </tr>
            <tr>
                <td>&lt;nav&gt;</td>
                <td>HTML 문서의 탐색 링크를 정의함.</td>
            </tr>
            <tr>
                <td>&lt;section&gt;</td>
                <td>HTML 문서에서 섹션(section) 부분을 정의함.</td>
            </tr>
            <tr>
                <td>&lt;article&gt;</td>
                <td>HTML 문서에서 독립적인 하나의 글(article) 부분을 정의함.</td>
            </tr>
            <tr>
                <td>&lt;aside&gt;</td>
                <td>HTML 문서에서 페이지 부분 이외의 콘텐츠(content)를 정의함.&nbsp;</td>
            </tr>
            <tr>
                <td>&lt;footer&gt;</td>
                <td>HTML 문서나 섹션(section) 부분에 대한 푸터(footer)를 정의함.</td>
            </tr>
        </tbody>
    </table>

- ### table 요소를 이용한 레이아웃

    table 요소를 이용하여 레이아웃을 작성하는 방법은 오래전에 사용하던 방식이며, 현재는 거의 사용하지 않는다.<br>
    table 요소는 레이아웃을 만들기 위해 설계된 요소가 아니라서, 테이블로 작성된 레이아웃은 수정이 매우 힘들다.<br>
    따라서 되도록이면 사용하지 않는 편이 좋다.

    <table width="100%" style="text-align:center; border:none">
        <tr>
            <td colspan="2" style="background-color:lightgrey"><h2>Header 영역</h2></td>
        </tr>
        <tr>
            <td style="background-color:#339999; color:white; width:30%"><h2>Nav 영역</h2></td>
            <td style="height:200px; text-align:left; background:crimson; color:#fff;"><p>SECTION 영역<br>SECTION 영역<br>SECTION 영역</p></td>
        </tr>
        <tr>
            <td colspan="2" style="background-color:#FFCC00"><h2>Footer 영역</h2></td>
        </tr>
    </table>





```
문법
<태그이름 style="속성이름 : 속성값"></태그이름>
```

```html
<p style="margin: 0;">style 속성을 이용한 배경색 변경</p>
```

<div style="background:#eee; padding: 20px; box-sizing: border-box; border-radius: 10px; color: black;">
    <strong style="display: block; padding-bottom: 20px;">▶ 실행결과</strong>
</div>

- ### 소제목

    ```
    문법
    <태그이름 style="속성이름 : 속성값"></태그이름>
    ```

    ```html
    <p style="margin: 0;">style 속성을 이용한 배경색 변경</p>
    ```

    <div style="background:#eee; padding: 20px; box-sizing: border-box; border-radius: 10px; color: black;">
        <strong style="display: block; padding-bottom: 20px;">▶ 실행결과</strong>
    </div>

<br><br>

## 출처

[TCP SCHOOL HTML](http://www.tcpschool.com/html/intro)
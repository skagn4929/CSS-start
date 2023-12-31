# CSS
- [CSS 강의](https://www.opentutorials.org/course/3086)

본 강의를 통해 CSS를 학습하고 정리한 내용입니다.

---
## 1. CSS란?
HTML 등의 마크업 언어로 작성된 문서가 실제로 웹사이트에 표현되는 방법을 정해주는 스타일 시트 언어이다.   
쉽게 말해 웹페이지를 디자인하는 언어라고 할 수 있다.

- Cascading Style Sheet의 약자.
- HTML로부터 디자인적인 요소를 분리해 정의할 수 있다.
- 자바스크립트와 연계해 동적인 콘텐츠 표현이나 디자인 적용이 가능하다.

## 2. 기본 문법 - 선택자와 속성
CSS 문법은 선택자와 속성으로 구성되어 있는데, 기본 구조는 다음과 같다.
```CSS
선택자 { (스타일 속성): (스타일 값); }


ex) h1 태그의 색상을 빨간색으로 적용

    h1 { color: red; }
```
- 선택자는 디자인을 적용하고자 하는 HTML 요소.
    - `*` : 전체 선택자
    - `.class` : 해당 class의 요소를 선택
    - `#id` : 해당 id의 요소를 선택
- 중괄호 {   } 를 선언부라 하며, 선택자가 지정한 태그에 어떠한 효과를 줄 것인가에 해당하는 부분이다.
- 세미콜론 ; 은 하나의 선택자에 대해 여러 개의 효과를 지정할 때 구분자로 쓰인다.

## 3. 박스 모델

![3](https://github.com/skagn4929/CSS-start/assets/134206709/6d5c9ec0-4bf9-4443-a747-908c2ab89680)

- **블록 레벨 요소** : 화면 전체를 쓰는 태그. ex) h1~h6 제목태그, p 태그, div 태그 등
- **인라인 요소** : 자기 자신의 콘텐츠 크기만큼 쓰는 태그. ex) span 태그, a 태그 등
- 이러한 요소들은 display 속성을 사용하여 언제든 바꿀 수 있다.
 
## 4. 그리드(Grid)
웹페이지를 위한 2차원 레이아웃 시스템. 이 기능을 통해 콘텐츠를 행과 열에 배치할 수 있으며 복잡한 레이아웃을 직관적으로 구축할 수 있다.

### 4-1. 그리드 구조
![4](https://github.com/skagn4929/CSS-start/assets/134206709/7d36ff53-a88d-487e-8e76-c22b8184498e)

- **그리드 컨테이너 (Grid Container)** : Grid의 전체 영역
- **그리드 아이템 (Grid Item)** : Grid 컨테이너의 자식 요소들
- **그리드 트랙 (Grid Track)** : Grid의 행(Row) 또는 열(Column)
- **그리드 셀 (Grid Cell)** : Grid의 한 칸
- **그리드 라인(Grid Line)** : Grid 셀을 구분하는 선
- **그리드 번호(Grid Number)** : Grid 라인의 각 번호
- **그리드 갭(Grid Gap)** : Grid 셀 사이의 간격
- **그리드 영역(Grid Area)** : Grid 라인으로 둘러싸인 사각형 영역으로, 그리드 셀의 집합

### 4-2. 그리드 적용
```css
ex)

.container {
    display: grid;
    grid-template-columns: 100px 1fr;
    grid-template-rows: 100px 1fr;
}
```
- `display: grid;` : 컨테이너의 속성을 그리드로 정의.
- `grid-template-columns` : 그리드 열 크기 속성
- `grid-template-rows` : 그리드 행 크기 속성
- `fr` : 공간 비율로도 설정 가능.

## 5. 미디어 쿼리
화면 크기에 따라 웹페이지의 각 요소가 반응해서 최적화된 모양으로 바뀌는 것을 반응형 웹 디자인이라 하며   
미디어 쿼리는 반응형 웹 디자인의 핵심 부분이다.

- 미디어 쿼리 적용
```css
ex)

@media(max-width: 800px) {
    div {
        display: none;
    }
}

: 화면 크기가 800px보다 작으면 <div>가 사라짐.
```
1. HTML 문서에 연결된 CSS 파일(외부 스타일 시트) 또는 <style> 태그 내부의 CSS 코드에서 미디어 쿼리를 정의.
2. 정의된 미디어 쿼리의 괄호 안에 있는 지정된 조건을 평가한다. 조건은 미디어 특성과 연산자로 구성된다.
3. 조건이 참이면, 미디어 쿼리 내부에 있는 스타일 규칙이 적용된다.

---
## 결과물
- https://skagn4929.github.io/CSS-start/2.html

![Screenshot 2023-07-09 at 18 43 38](https://github.com/skagn4929/CSS-start/assets/134206709/413ff882-b179-453c-b425-bb14ea6c5118)

- HTML
```HTML
<!DOCTYPE html>
<html>
  <head>
    <title>WEB1 - CSS</title>
    <meta charset="utf-8" />
    <link rel="stylesheet" href="style.css" />
  </head>
  <body>
    <h1><a href="index.html">WEB</a></h1>
    <div id="grid">
      <ol>
        <li><a href="1.html">HTML</a></li>
        <li><a href="2.html">CSS</a></li>
        <li><a href="3.html">JavaScript</a></li>
      </ol>
      <div id="article">
        <h2>CSS</h2>
        <p>
          ...생략...
        </p>
      </div>
    </div>
  </body>
</html>
```

- CSS
```css
a {
  color: black;
  text-decoration: none;
}
h1 {
  font-size: 45px;
  text-align: center;
  border-bottom: 1px solid gray;
  margin: 0px;
  padding: 20px;
}
#grid ol {
  border-right: 1px solid gray;
  width: 100px;
  margin: 0;
  padding: 20px;
  padding-left: 33px;
}
body {
  margin: 0px;
}
#grid {
  display: grid;
  grid-template-columns: 150px 1fr;
}
#article {
  padding-left: 25px;
}
@media (max-width: 800px) {
  #grid {
    display: block;
  }
  #grid ol {
    border-right: none;
  }
  h1 {
    border-bottom: none;
  }
}
```


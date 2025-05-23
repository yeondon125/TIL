# CSS

## CSS 기본 문법 및 Selector 사용법

```css
선택자 {
  속성: 값;
  속성: 값;
}
```

**기본 선택자**

> - 전체 선택 `\* { margin: 0; }`
> - #id 단일 아이디 선택 `#id { margin: 0; }`
> - .class 단일 클래스 선택 `.class { margin: 0; }`
> - 태그명 특정 태그 `h1 { color: red; }`

**결합 선택자**

> - A B
>   > A 안에 있는 B `div p { color: green; }`
> - A > B
>   > A 바로 아래 자식 `B ul > li { list-style: none; }`
> - A + B
>   > A 바로 다음 형제 `B	h1 + p { margin-top: 0; }`
> - A ~ B
>   > A 이후 모든 형제 `B	h1 ~ p { color: gray; }`

## 글꼴, 색상, 배경 등 기초 스타일링

```css
body {
  margin: 0;
  padding: 0;
  font-family: "맑은 고딕", "Malgun Gothic", "돋움", "Dotum", "굴림", "굴림체",
    sans-serif;
  color: #333;
  background-color: #f5f5f5;
}
```

**Font**

> font-family
>
> > 글꼴 종류 설정  
> > `font-family: 'Arial', sans-serif;`
>
> font-size
>
> > 글꼴 크기 설정  
> > `font-size: 14px;`
>
> font-weight
>
> > 글꼴 굵기 설정  
> > `font-weight: bold;`
>
> font-style
>
> > 글꼴 스타일 설정  
> > `font-style: italic;`
>
> font-align
>
> > 글 정령  
> > `font-align: center;`

**color**

> color
>
> > 글자 색상 설정  
> > `color: red;`, `color: #ff0000;`, `color: rgb(255, 0, 0)`, `color: rgba(255, 0, 0, 0.5);`

**background**

> background-color
>
> > 배경색 설정  
> > `background-color: skyblue;`
>
> background-image
>
> > 배경 이미지 설정  
> > `background-image: url(./images/1.png);`
>
> background-repeat
>
> > 배경 이미지 반복 설정  
> >  `background-repeat: no-repeat;`
>
> background-position
>
> > 배경 이미지 위치 설정  
> > `background-position: center;`
>
> background-size
>
> > 배경 이미지 크기 설정  
> > `background-size: cover;`

## Box Model 이해

**Box Model**
| 부분 | 설명 | 예시 CSS 속성 |
|-------------|--------------------------------------|----------------------------|
| Content | 실제 내용 (텍스트, 이미지 등) | `width`, `height` |
| Padding | 내용과 테두리 사이의 안쪽 여백 | `padding: 10px;` |
| Border | 요소의 테두리 (외곽선) | `border: 1px solid black;` |
| Margin | 요소 바깥쪽의 공간 (다른 요소와의 거리) | `margin: 20px;` |

![alt text](image.png)

## 레이아웃 이해

**display**

- HTML 구조가 어떤식으로 보일지를 결정하는 속성
  | 값 | 설명 | 특징/사용 예시 |
  |----|-----|---------------|
  | block | 줄 전체를 차지함 | `div`, `p`, `h1` 등 |
  | inline | 내용 크기만큼 차지 | `span`, `a` 등 |
  | inline-block | inline처럼 흐르면서 block처럼 크기 지정 가능 | 버튼 여러 개 나열할 때 |
  | none | 화면에 표시하지 않음 | 요소 숨기기 |
  | flex | Flexbox 레이아웃 시작 | 수평/수직 정렬 쉽게 |
  | grid | Grid 레이아웃 시작 | 복잡한 2D 레이아웃 구현 |

## flexbox

- 가로나 세로 한방향을 기준으로 레이아웃을 편하게 관리할 수 있는 레이아웃 기법. 수직 정렬이나 크기 조정 등에 사용된다.

**1. display: flexbox**

> Flexbox 레이아웃 시작
>
> ```css
> .flexbox {
>   display: flexbox;
> }
> ```

**2. flex-direction**

> 주축 방향 설정
>
> - `row` : 수평 방향으로 정렬
> - `row-reverse` : 수평 방향으로 정렬 (역순)
> - `column` : 수직 방향으로 정렬
> - `column-reverse` : 수직 방향으로 정렬 (역순)
>
> ```css
> .flexbox {
>   display: flexbox;
>   flex-direction: row-reverse;
> }
> ```

**3. justify-content**

> 주축 정렬
>
> - `flex-start` : 왼쪽 정렬
> - `center` : 가운데 정렬
> - `flex-end` : 오른쪽 정렬
> - `space-between` : 일정한 간격을 두고 좌우로 분포 (처음과 끝 간격 없음음)
> - `space-around` : 일정한 간격을 두고 좌우로 분포 (처음과 끝 간격 있음)
> - `space-evenly` : 처음과 끝 간격이 모두 동일하게 분포
>
> ```css
> .flexbox {
>   display: flexbox;
>   justify-content: space-between;
> }
> ```

**4. align-items**

> 교차축 정렬
>
> - `stretch` : 요소의 수직 축 방향으로 쭉 늘어져 정렬
> - `center` : 가운데 정렬
> - `flex-start` : 아이템들을 시작점으로 정렬
> - `flex-end` : 아이템들을 끝점으로 정렬
> - `baseline` : 텍스트 베이스라인에 따라 정렬
>
> ```css
> .flexbox {
>   display: flexbox;
>   align-items: center;
> }
> ```

**5. align-content**

> 여러 줄 교차축 정렬  
> `flex:wrap;` `flex-direction: column;` 이 설정된 상황에서 아이템이 두줄 이상 되었을 때 사용함
>
> - `flex-start` : 시작점으로 정렬
> - `flex-end` : 끝점으로 정렬
> - `center` : 가운데 정렬
> - `space-between` : 일정한 간격을 두고 좌우로 분포 (처음과 끝 간격 없음)
> - `space-around` : 일정한 간격을 두고 좌우로 분포 (처음과 끝 간격 있음)
> - `space-evenly` : 처음과 끝 간격이 모두 동일
>
> ```css
> .flexbox {
>   display: flexbox;
>   flex-wrap: wrap;
>   align-content: space-around;
> }
> ```

**6. flex-wrap**

> 줄바꿈 여부 설정
>
> - `flex-wrap: wrap;` : 가로로 끊어서 여러줄로 나누어 출력
> - `flex-wrap: nowrap;` : 한줄로 출력
> - `flex-wrap: wrap-reverse;` : 가로로 끊어서 여러줄로 나누어 출력 후 역순으로 출력
>
> ```css
> .flexbox {
>   display: flexbox;
>   flex-wrap: wrap;
> }
> ```

**7. gap**

> 선택된 요소 끼리 간격을 지정함
>
> ```css
> .flexbox {
>   display: flexbox;
>   gap: 20px;
> }
> ```

**8. lex-basis**

> Flex 아이템의 기본 크기를 설정함
> 위에서 설정한 축 방향으로 크기가 증가한다
>
> ```css
> .flexbox {
>   display: flexbox;
>   flex-basis: 100px;
> }
> ```

**9. flex-grow**

> 컨테이너에 공간이 남으면 얼마나 크기를 할당할 지 설정함
>
> ```css
> .flexbox {
>   display: flexbox;
>   flex-grow: 1;
> }
> ```

**10. flex-shrink**

> 컨테이너에 공간이 부족하면 얼마나 크기를 줄일지 설정함
>
> ```css
> .flexbox {
>   display: flexbox;
>   flex-shrink: 1;
> }
> ```

## grid

가로와 세로 2차원 레이아웃을 다룰 때 사용되는 기능

**1. display: grid**

> gird 디스플레이 시작
>
> ```css
> .grid {
>   display: grid;
> }
> ```

**2. grid-template-columns / grid-template-rows**

> 각 요소에 대한 크기를 설정함
>
> ```css
> .grid {
>   display: grid;
>   grid-template-columns: 100px 100px; //좌, 우 크기설정
>   grid-template-rows: 100px 100px; //상, 하 크기설정
> }
> ```

**3. gap (grid-gap)**

> 요소 간 간격 설정  
> `row-gap` 세로 간격 설정
> `column-gap` 가로 간격 설정
>
> ```css
> .grid {
>   display: grid;
>   grid-template-columns: 100px 100px; //좌, 우 크기설정
>   grid-template-rows: 100px 100px; //상, 하 크기설정
>   grid-gap: 10px; //간격 설정
> }
> ```

**4. grid-column / grid-row**

> 각 요소가 배치되는 위치 설정  
> `grid-column:start` : 가로 차지할 공간 시작부분 설정  
> `grid-column-end` : 가로 차지할 공간 끝부분 설정  
> `grid-row-start` : 세로 차지할 공간 시작부분 설정  
> `grid-row-end` : 세로 차지할 공간 끝부분 설정
>
> `grid-column: 1 / 3;` : 시작, 끝부분 한번에 설정  
>  `grid-row: 1 / 2;` : 시작 끝부분 한번에 설정
>
> ```css
> .item:nth-child(1) {
>   grid-column-start: 1;
>   grid-column-end: 3;
>   grid-row-start: 1;
>   grid-row-end: 2;
> }
> ```
>
> ```css
> .item:nth-child(1) {
>   grid-column: 1 / 3;
>   grid-row: 1 / 2;
> }
> ```
>
> 둘이 같은 코드임

**5. justify-items / align-items**

> 컨테이너 안 요소가 배치되는 위치 설정  
> `justify-items: center;` : 가로방향 가운데 정렬  
> `align-items: center;` : 세로방향 가운데 정렬
>
> ```css
> .item {
>   justify-items: center;
>   align-items: center;
> }
> ```

**6. justify-content / align-content**

> 컨테이너 안 요소 높이와 넓이 크기가 컨테이너 크기보다 작을 때, 요소들을 모두 정렬하는 태그  
> `justify-content: center;` : 가로방향 가운데 정렬  
> `align-content: center;` : 세로방향 가운데 정렬
>
> ```css
> .item {
>   justify-content: center;
>   align-content: center;
> }
> ```

**7. grid-template-areas / grid-area**

> `grid-template-areas` : 그리드 레이아웃을 이름으로 설계하는 방식
>
> ```css
> .container {
>   display: grid;
>   grid-template-areas:
>     "header header"
>     "sidebar main"
>     "footer footer";
> }
> ```

> `grid-area` : 각 자식 요소에게 grid에서 차지할 영역 이름을 지정해주는 속성입니다.
>
> ```html
> <div class="container">
>   <div class="header">Header</div>
>   <div class="sidebar">Sidebar</div>
>   <div class="main">Main</div>
>   <div class="footer">Footer</div>
> </div>
> ```
>
> ```css
> .header {
>   grid-area: header;
> }
> .sidebar {
>   grid-area: sidebar;
> }
> .main {
>   grid-area: main;
> }
> .footer {
>   grid-area: footer;
> }
> ```

- 자식 요소는 grid-area를 통해 어디에 배치될지 결정.

- 부모의 grid-template-areas 값과 이름이 반드시 일치해야 합.

```css

.container {
  display: grid;
  grid-template-columns: 200px 1fr;
  grid-template-rows: 60px 1fr 50px;
  grid-template-areas:
    "header header"
    "sidebar main"
    "footer footer";
  height: 100vh;
  gap: 10px;
}

.header  { grid-area: header; background: lightblue; }
.sidebar { grid-area: sidebar; background: lightgray; }
.main    { grid-area: main; background: white; }
.footer  { grid-area: footer; background: lightcoral; }
</style>

<div class="container">
  <div class="header">Header</div>
  <div class="sidebar">Sidebar</div>
  <div class="main">Main Content</div>
  <div class="footer">Footer</div>
</div>
```

## position

**1. static (기본값)**

> 대부분 모든 요소 기본값이다.  
> 그냥 배치대로 진행된다.
>
> ![alt text](image-1.png)

**2. relative (상대 위치)**

> 자기 자리는 유지한 상태로 설정한 값만큼 이동한다.
>
> ```CSS
> div {
>  position: relative;
>  top: 20px;
>  left: 10px;
> }
> ```

![alt text](image-2.png)

**3. absolute (절대 위치)**

> 자기 자리는 유지하지 않는다.  
> 부모 요소의 위치에 따라 이동한다.
> position이 relative, fixed, absolute 하나라도 있으면 그 부모를 기준으로 절대적으로 이동한다.
>
> ```css
> .container {
>   position: relative;
> }
> .child {
>   position: absolute;
>   top: 0;
>   left: 0;
> }
> ```

**4. position: fixed (고정 위치)**

> 브라우저 창을 기준으로 고정한다.  
> 스크롤을 내려도 항상 그 자리에 있다.  
> 광고 배너, 상단 메뉴 등에 많이 사용한다.
>
> ```css
> .fixed-banner {
>   position: fixed;
>   top: 0;
>   left: 0;
> }
> ```

**5. position: sticky (스크롤 시 고정)**

> 스크롤을 내리다가 요소가 top: 0 위치에 도달하면 고정된다.
> 그 전까지는 원래 위치에 있다.
>
> ```css
> .sticky-title {
>   position: sticky;
>   top: 0;
> }
> ```

## 반응형 웹

> 하나의 코드와 URL 로 다양한 크기에 따른 레이아웃이 변하는 웹 사이트를 의미한다.
>
> **em**  
> : 자신을 포함하고 있는 요소의 폰트크기를 1로 하는 단위이다.
>
> **rem**  
> : root, 즉 가장 css 에서 가장 상위요소의 폰트크기를 1로 하는 단위이다.
>
> **media querie**  
> : 특정 조건에 따라 스타일을 적용하는 방식이다
>
> > - `prefers-color-scheme: dark` : 다크모드인가?
> > - `max-width: 600px` : 최대 넓이가 600px 이하일 때
> > - `min-width: 1024px` : 최소 넓이가 1024px 이상일 때
>
> ```css
> /* 모바일 우선 접근 */
> @media (max-width: 600px) {
>   .menu {
>     display: none;
>   }
> }
>
> /* 데스크탑 전용 스타일 */
> @media (min-width: 1024px) {
>   .menu {
>     display: block;
>   }
> }
> ```

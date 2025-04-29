# FE

## CSS

### CSS 기본 문법 및 Selector 사용법

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

### 글꼴, 색상, 배경 등 기초 스타일링

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

### Box Model 이해

**Box Model**
| 부분 | 설명 | 예시 CSS 속성 |
|-------------|--------------------------------------|----------------------------|
| Content | 실제 내용 (텍스트, 이미지 등) | `width`, `height` |
| Padding | 내용과 테두리 사이의 안쪽 여백 | `padding: 10px;` |
| Border | 요소의 테두리 (외곽선) | `border: 1px solid black;` |
| Margin | 요소 바깥쪽의 공간 (다른 요소와의 거리) | `margin: 20px;` |

### 레이아웃 이해

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

### flexbox

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

**10. `flex-shrink**

> 컨테이너에 공간이 부족하면 얼마나 크기를 줄일지 설정함
>
> ```css
> .flexbox {
>   display: flexbox;
>   flex-shrink: 1;
> }
> ```

### grid

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

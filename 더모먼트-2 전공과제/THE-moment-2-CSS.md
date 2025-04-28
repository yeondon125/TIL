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

**Flexbox**

- 가로나 세로 한방향을 기준으로 레이아웃을 편하게 관리할 수 있는 레이아웃 기법. 수직 정렬이나 크기 조정 등에 사용된다.

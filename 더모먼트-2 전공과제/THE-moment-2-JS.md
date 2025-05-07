# JS 기본 문법

## 1. 변수 선언

> 변수 선언은 var, let, const로 가능함.
>
> `let` : 변경 가능한 변수
>
> `const` : 변경 불가능한 변수
>
> `var` : 사용하지 않는 것이 좋음
>
> ```js
> let a = 10;
> const b = 20;
> ```

## 2. 출력

> `console.log()` : 출력하는 함수
>
> ```js
> console.log("Hello World");
> ```
>
> 브라우저 콘솔창이나 터미널에 출력됨
>
> ```js
> let name = 철수;
> console.log(name + "는 남자다.");
> console.log("${name} + 는 남자다.");
> console.log("남자의 이름은? ", name);
> ```
>
> 변수와 문자열을 같이 출력할 때는 위와 같은 방법을 사용함

## 3. 조건문

> `if`, `else` 를 사용하여 c언어와 크게 다르지 않음
>
> 비교연산자 `==`와`!=` 는 값만 같거나 다른지 판단하고  
> 비교연산자 `===`와`!==` 는 값과 타입이 모두 같거나 다른지 판단함
>
> ```js
> let score = 85;
>
> if (score >= 90) {
>   console.log("A 학점");
> } else if (score >= 80) {
>   console.log("B 학점");
> } else {
>   console.log("C 이하");
> }
> ```

| 연산자 | 이름         | 역할                         | 결과 예시                                                       | 주의사항                      |
| ------ | ------------ | ---------------------------- | --------------------------------------------------------------- | ----------------------------- |
| `&&`   | AND (그리고) | 앞이 true일 때만 뒤 평가     | `3 && 5` → `5`, `0 && 5` → `0`                                  | **값 자체 반환**              |
| `\|\|` | OR (또는)    | 앞이 true면 바로 반환        | `0 \|\| "손님"` → `"손님"`, `"홍길동" \|\| "손님"` → `"홍길동"` | **단락 평가 (short-circuit)** |
| `!`    | NOT (부정)   | true → false / false → true  | `!true` → `false`, `!0` → `true`                                | boolean으로 변환됨            |
| `!!`   | double NOT   | 값을 명확한 boolean으로 바꿈 | `!!"철수"` → `true`, `!!0` → `false`                            | `true/false`로 강제 변환      |

## 4. 반복문

| 문법         | 설명               | 예시 대상                |
| ------------ | ------------------ | ------------------------ |
| `for`        | 일반 반복문        | 숫자 기반 반복           |
| `while`      | 조건 반복문        | 무한 루프 또는 조건 판단 |
| `do...while` | 최소 1회 실행 보장 | 사용자 입력 대기 등      |
| `for...of`   | 배열 요소 반복     | `[1,2,3]`, `"문자열"`    |
| `for...in`   | 객체 key 반복      | `{ name: "영희" }`       |

### 4.1 for 반복문

```js
for (let i = 0; i < 5; i++) {
  console.log("i =", i);
}
```

c언어와 같은 방식으로 사용

### 4.2 while 반복문

```js
let i = 0;
while (i < 5) {
  console.log("i =", i);
  i++;
}
```

반복문이 끝날 때까지 반복
c언어와 같은 방식으로 사용

### 4.3 do...while 반복문

```js
let i = 0;
do {
  console.log("i =", i);
  i++;
} while (i < 5);
```

반복문이 끝날 때까지 반복  
c언어와 같은 방식으로 사용

### 4.4 for...of 반복문

```js
const array = ["1번", "2번", "3번"];

for (const element of array) {
  console.log(element); // 배열[0] ~ 끝까지 순차적 출력
  console.log(array); // 배열 전체 출력
}
```

배열의 처음 값부터 끝까지 순차적으로 출력  
배열의 요소를 꺼내어 출력할 때 유용함

## 5. 함수

함수 선언

```js
function 함수이름(매개변수1, 매개변수2) {
  // 실행할 코드
  return 결과값;
}
```

함수 표현식

```js
const sayHi = function (name) {
  console.log(`안녕, ${name}님`);
};

sayHi("철수"); // 출력: 안녕, 철수님
```

## 6. 배열

여러 개의 값을 한 변수에 저장할 수 있는 자료형  
순서(인덱스)가 있음 → 0부터 시작함

### 배열선언

```js
let fruits = ["사과", "바나나", "포도"];
const numbers = [1, 2, 3, 4, 5];
```

### 배열 접근

```js
console.log(fruits[0]); // "사과"
console.log(fruits[1]); // "바나나"
```

### 배열 추가, 삭제

```js
fruits.push("오렌지"); // 맨 뒤에 추가
fruits.pop(); // 맨 뒤에서 삭제

fruits.unshift("딸기"); // 맨 앞에 추가
fruits.shift(); // 맨 앞에서 삭제
```

### 배열 반복

```js
for (let i = 0; i < fruits.length; i++) {
  console.log(fruits[i]);
}

for (const fruit of fruits) {
  console.log(fruit);
}
```

## 7. 객체

이름(키)과 값(value)을 쌍으로 저장하는 자료형  
순서 없음, 대신 key로 접근함

### 객체 선언

```js
const person = {
  name: "철수",
  age: 20,
  isStudent: true,
};
```

### 객체 접근

```js
console.log(person.name); // "철수"
console.log(person["age"]); // 20
```

### 객체 추가, 삭제

```js
person.city = "서울"; // 추가
person.age = 21; // 수정
delete person.isStudent; // 삭제
```

### 객체 반복

```js
for (const key in person) {
  console.log(key, person[key]);
}
```

# DOM 선택자 및 조작

HTML 문서 안에 있는 요소들(h1, p, div 등)을

자바스크립트로 찾아서 바꾸는 것

## 1. 요소 선택

| 메서드                              | 설명                               | 예시                                      |
| ----------------------------------- | ---------------------------------- | ----------------------------------------- |
| `document.querySelector()`          | CSS 선택자 방식으로 1개 요소 선택  | `document.querySelector("h1")`            |
| `document.querySelectorAll()`       | CSS 선택자 방식으로 여러 요소 선택 | `document.querySelectorAll(".item")`      |
| `document.getElementById()`         | `id`로 요소 선택                   | `document.getElementById("title")`        |
| `document.getElementsByClassName()` | 클래스명으로 여러 요소 선택        | `document.getElementsByClassName("item")` |

```html
<h1 id="title">안녕</h1>
<p class="desc">내용1</p>
<p class="desc">내용2</p>
```

```js
const title = document.getElementById("title"); //title 변수에 title id를 가지고 있는 <h1> 태그 대입
const firstParagraph = document.querySelector(".desc");
const allParagraphs = document.querySelectorAll(".desc");
```

## 2. 요소 조작

### 2.1 택스트, html 변경경

| 속성        | 설명                     | 예시                                 |
| ----------- | ------------------------ | ------------------------------------ |
| `innerText` | 요소의 **텍스트만** 변경 | `title.innerText = "반가워!"`        |
| `innerHTML` | HTML 태그 포함해서 변경  | `title.innerHTML = "<i>반가워!</i>"` |

```js
title.innerText = "제목 바뀜"; // 텍스트만 바뀜
title.innerHTML = "<b>굵게 바뀜</b>"; // 태그까지 적용됨
```

### 2.2 css 스타일 변경

```js
title.style.color = "red";
title.style.fontSize = "30px";
```

### 2.3 클래스 조작

```js
title.classList.add("active"); // 클래스 추가
title.classList.remove("active"); // 클래스 제거
title.classList.toggle("active"); // 있으면 제거, 없으면 추가
```

## 3. 이벤트 연결

```js
const button = document.querySelector("button");

button.addEventListener("click", function () {
  alert("버튼 클릭됨!");
});
```

브라우저에서 클릭 했는지 안했는지 판단하고  
만약 클릭 했다면 아래 코드가 실행됨

# 이벤트 처리 (addEventListener, 클릭/입력 이벤트)

사용자의 동작(클릭, 입력 등)에 반응하는 코드  
자바스크립트에서 이벤트를 감지하고, 처리할 수 있음

## addEventListener

`요소.addEventListener("이벤트이름", 함수)` : 해당 이벤트가 발생하면 함수를 실행

```js
const btn = document.querySelector("button");

btn.addEventListener("click", function () {
  console.log("버튼 클릭됨!");
});
```

## 클릭 이벤트

```html
<button id="btn">눌러봐!</button>

<script>
  const btn = document.getElementById("btn");

  btn.addEventListener("click", function () {
    alert("버튼이 클릭됨!");
  });
</script>
```

## 입력 이벤트 (input, change, keyup, keydown)

| 이벤트 이름 | 설명                           | 예시 대상       |
| ----------- | ------------------------------ | --------------- |
| `click`     | 클릭할 때                      | 버튼, 링크 등   |
| `input`     | 입력 값이 바뀔 때              | input, textarea |
| `change`    | 값이 변경되고 포커스 벗어날 때 | input, select   |
| `submit`    | 폼 전송될 때                   | form            |
| `mouseover` | 마우스가 올라갔을 때           | 모든 요소       |
| `keydown`   | 키보드 키 눌렸을 때            | input           |

### input

> 입력 필드에 글자가 변할 때마다 실행

```html
<input type="text" id="name" placeholder="이름 입력" />

<script>
  const input = document.getElementById("name");

  input.addEventListener("input", function () {
    console.log("입력값:", input.value);
  });
</script>
```

### change

> 입력을 완료하고 포커스가 벗어났을 때 실행됨

```js
input.addEventListener("change", function () {
  console.log("최종 입력값:", input.value);
});
```

### keyup / keydown

> 키보드를 눌렀을 때 실행됨

```js
input.addEventListener("keydown", function () {
  console.log("키 눌림");
});

input.addEventListener("keyup", function () {
  console.log("키 뗌");
});
```

# 비동기 개념 소개

> 자바스크립트에서 시간이 오래 걸리는 작업(서버 요청 등)을  
> 멈추지 않고 처리하기 위한 방법

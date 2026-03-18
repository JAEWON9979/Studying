# JavaScript 기초 (초보자용)

이 문서는 JavaScript의 기본 개념과 자주 쓰는 문법을 아주 쉽게 정리한 메모입니다.

---

## 1) JavaScript란?
- 브라우저에서 동작하는 프로그래밍 언어로, HTML/CSS와 함께 웹을 만듭니다.
- HTML은 구조, CSS는 스타일, JS는 동작(이벤트 처리, 데이터 조작 등)을 담당합니다.

---

## 2) JS 연결 방법
- 외부 파일 연결(권장): `<script src="app.js" defer></script>`
  - `defer`를 쓰면 HTML 로드 후 스크립트가 실행됩니다.
- 인라인(간단한 예시): `<script>console.log('hello')</script>`

예시 (HTML 안):
```html
<!-- head에 넣을 때 -->
<script src="app.js" defer></script>
```

---

## 3) 기본 문법
- 출력(디버그): `console.log('메시지')`
- 변수: `let`(변경 가능), `const`(변경 불가)
```js
let x = 5;
const name = '길동';
```
- 자료형 예: 숫자, 문자열, 불리언, 배열, 객체
```js
const arr = [1, 2, 3];
const obj = { name: '홍길동', age: 30 };
```

---

## 4) 함수
- 선언식 함수:
```js
function add(a, b) {
  return a + b;
}
```
- 화살표 함수(간단):
```js
const add = (a, b) => a + b;
```

---

## 5) 조건문과 반복문
```js
if (x > 10) {
  // 실행
} else {
  // 다른 실행
}

for (let i = 0; i < 5; i++) {
  console.log(i);
}
```

---

## 6) DOM(문서 객체 모델) 기초
- HTML 요소를 선택하고 조작하는 방법입니다.
```js
const el = document.getElementById('myId');
const el2 = document.querySelector('.myClass');
el.textContent = '안녕하세요';
el.style.color = 'red';
```
- 이벤트 연결 예:
```js
const btn = document.querySelector('button');
btn.addEventListener('click', function() {
  alert('버튼 클릭!');
});
```

---

## 7) 간단한 예제: 버튼 클릭 시 텍스트 변경
HTML:
```html
<button id="myBtn">클릭</button>
<p id="msg">초기 텍스트</p>
<script src="app.js" defer></script>
```
app.js:
```js
const btn = document.getElementById('myBtn');
const msg = document.getElementById('msg');
btn.addEventListener('click', () => {
  msg.textContent = '버튼이 눌렸습니다!';
});
```

---

## 8) 비동기 기초 (fetch)
- 서버에서 데이터를 가져올 때 사용합니다.
```js
fetch('https://api.example.com/data')
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(err => console.error(err));
```
- async/await 문법:
```js
async function loadData() {
  try {
    const res = await fetch('https://api.example.com/data');
    const data = await res.json();
    console.log(data);
  } catch (e) {
    console.error(e);
  }
}
```

---

## 9) 디버깅 팁
- `console.log()`로 변수 값을 확인하세요.
- 브라우저 개발자 도구(F12)의 Console과 Sources 탭을 활용하세요.
- 에러가 나면 에러 메시지를 읽고, 해당 줄을 확인합니다.

---

## 10) 초보자 팁
- 먼저 `console.log`로 동작을 확인해 보세요.
- 작은 기능(버튼 클릭 하나)부터 만들어 보며 익히세요.
- DOM 선택자(`getElementById`, `querySelector`)와 `addEventListener`를 자주 연습하세요.

---

원하시면 예제를 더 늘려 `폼 검증`, `간단한 Todo 앱`, 또는 `localStorage` 사용 예시를 만들어 드리겠습니다.

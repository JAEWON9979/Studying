# CSS 기초 (초보자용)

이 문서는 CSS의 기본 개념과 자주 쓰는 속성을 아주 쉽게 정리한 메모입니다.

---

## 1) CSS란?
- CSS는 웹 페이지의 '보이는 모양'을 정합니다. (색, 글자 크기, 여백 등)
- HTML로 뼈대를 만들고 CSS로 꾸밉니다.

---

## 2) CSS 연결 방법
- 외부 파일을 연결: HTML의 `<head>`에 넣음
```html
<link rel="stylesheet" href="styles.css">
```
- 인라인 스타일(권장하지 않음): 태그 안에 `style` 속성 사용
```html
<p style="color: red;">빨간 글자</p>
```
- 내부 스타일: `<style>` 태그 사용 (간단한 테스트용)

---

## 3) 선택자(Selector)
- 요소 선택자: `p`, `h1` 등
- 클래스 선택자: `.my-class` (여러 요소에 재사용 가능)
- 아이디 선택자: `#my-id` (한 페이지에 하나만 사용 권장)
- 하위 선택자: `nav a` (nav 안의 a만 선택)

예시:
```css
/* 모든 p 요소 */
p { color: #333; }
/* 클래스 */
.box { padding: 10px; }
/* 아이디 */
#header { background: #f0f0f0; }
```

---

## 4) 자주 쓰는 속성
- 색상과 배경
```css
color: blue;            /* 글자색 */
background-color: #fff; /* 배경색 */
```
- 글자 크기와 정렬
```css
font-size: 16px;
text-align: center;
```
- 여백 (외부/내부)
```css
margin: 10px;   /* 바깥 여백 */
padding: 8px;   /* 안쪽 여백 */
```
- 테두리
```css
border: 1px solid #ccc;
```
- 너비/높이
```css
width: 200px;
height: 100px;
```

---

## 5) 박스 모델(Box model)
- 요소는 컨텐츠(content) → 패딩(padding) → 테두리(border) → 마진(margin) 순으로 영역을 가집니다.
- `box-sizing: border-box;`를 사용하면 width/height가 테두리와 패딩을 포함하여 계산되어 다루기 쉽습니다.
```css
* { box-sizing: border-box; }
```

---

## 6) display 주요 값
- `block`: 줄 전체를 차지 (예: `div`, `p`)
- `inline`: 텍스트 흐름 안 (예: `span`, `a`)
- `inline-block`: inline처럼 흐르지만 너비/높이 지정 가능
- `none`: 화면에서 숨김 (DOM에는 남음)

---

## 7) Flexbox(기본)
- 레이아웃 정렬에 자주 사용되는 방법입니다. 간단한 사용법:
```css
.container { display: flex; /* 자식들이 한 줄로 배치됨 */ }
.container { justify-content: center; /* 가로 정렬 */ }
.container { align-items: center; /* 세로 정렬 */ }
```

---

## 8) 예시: 간단한 styles.css
```css
/* 전체 기본 글꼴과 박스 사이징 */
* { box-sizing: border-box; }
body { font-family: Arial, sans-serif; color: #222; }

/* 헤더 */
#header { background: #f8f8f8; padding: 20px; text-align: center; }

/* 버튼 스타일 */
.btn { display: inline-block; background: #007bff; color: #fff; padding: 8px 12px; border-radius: 4px; text-decoration: none; }
.btn:hover { background: #0056b3; }

/* 반응형 간단 예 */
@media (max-width: 600px) {
  .container { padding: 10px; }
}
```

간단한 HTML 연결 예시:
```html
<head>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <div id="header">안녕하세요</div>
  <a class="btn" href="#">클릭</a>
</body>
```

---

## 9) 초보자 팁
- 먼저 색과 여백, 글자 크기만 바꿔보며 연습하세요.
- 개발자 도구(F12)를 열어 스타일을 직접 수정해보면 빠르게 배울 수 있습니다.
- 클래스(`.class`)로 스타일을 재사용하도록 하세요. 너무 많은 인라인 스타일은 피하세요.

---

원하시면 `flexbox` 예제, `grid` 간단 설명, 또는 더 많은 CSS 속성(transition, transform 등)을 추가해 드릴게요.

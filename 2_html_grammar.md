# HTML 기초 (초보자용)

이 문서는 HTML의 가장 기본적인 태그와 사용법을 아주 쉽게 정리한 메모입니다.

---

## 1) 제목(Heading)
- 한 문서에는 보통 `h1`을 한 번만 사용합니다.
- `h2`, `h3`로 소제목을 나눌 수 있습니다.

예시 HTML:
```html
<h1>사이트 제목</h1>
<h2>섹션 제목</h2>
```

---

## 2) 문단(Paragraph)
- 문단은 `<p>`로 감쌉니다.
- 짧은 설명이나 본문을 적을 때 사용합니다.

예시 HTML:
```html
<p>이것은 한 문단입니다.</p>
```

---

## 3) 링크(Anchor)
- 다른 페이지로 이동할 때 `<a href="URL">텍스트</a>` 를 사용합니다.
- `target="_blank"`는 새 탭에서 링크를 엽니다.

예시 HTML:
```html
<a href="https://www.example.com" target="_blank">예시 사이트</a>
```

---

## 4) 이미지(Image)
- 이미지는 `<img src="경로" alt="대체텍스트">` 로 넣습니다.
- `alt`는 이미지가 로드되지 않을 때 또는 스크린 리더에서 보여지는 설명입니다. 꼭 작성하세요.

예시 HTML:
```html
<img src="https://via.placeholder.com/100" alt="작은 예시 이미지">
```

---

## 5) 리스트(List)
- 순서 없는 목록: `<ul>` 안에 `<li>` 항목을 넣습니다.
- 순서 있는 목록: `<ol>` 안에 `<li>`를 넣습니다.
- 중첩도 가능합니다 (리스트 안에 또 다른 리스트).

간단한 예:
```html
<ul>
  <li>사과</li>
  <li>바나나</li>
</ul>

<ol>
  <li>1단계</li>
  <li>2단계</li>
</ol>
```

설명(초보자용):
- <strong>ul</strong>은 순서가 필요 없는 항목(예: 쇼핑 목록)
- <strong>ol</strong>은 순서가 중요한 항목(예: 조리법 단계)

---

## 6) 폼(Form) — 입력 받기
- 폼은 사용자의 입력을 서버로 보낼 때 사용합니다.
- 중요한 속성들:
  - `action`: 데이터를 보낼 주소
  - `method`: `get` 또는 `post` (초보자는 `post`는 숨겨서, `get`은 URL에 붙음으로 기억)
  - `name`: 서버로 보낼 때 사용하는 키(무조건 필요)
  - `id` + `label for`는 접근성(화면 리더 등)에 중요
  - `required`는 필수 입력

간단한 폼 예시:
```html
<form action="/submit-example" method="post">
  <label for="name">이름:</label>
  <input id="name" name="name" type="text" placeholder="홍길동" required>

  <label for="email">이메일:</label>
  <input id="email" name="email" type="email" placeholder="me@example.com" required>

  <button type="submit">전송</button>
</form>
```

설명(초보자용):
- `name`이 있어야 서버에서 값을 받을 수 있어요.
- `label`을 클릭하면 입력창에 포커스가 가서 사용하기 편합니다.

---

## 7) 푸터(Footer)
- `footer`는 페이지의 아래쪽에 들어가는 정보(저작권, 연락처, 작은 링크 등)를 담습니다.

예시 HTML:
```html
<footer>
  <p>연락: info@example.com | © 2026</p>
</footer>
```

초보자에게 쉬운 팁:
- 푸터는 페이지마다 공통으로 넣는 정보(저작권, 이메일, 회사명 등)를 적습니다.

---

## 마무리
- 여기 적힌 태그들만 익혀도 간단한 정적 페이지를 만들 수 있습니다.
- 원하면 `checkbox`, `radio`, `select`, CSS 기초, 또는 더 많은 폼 예시를 추가해드릴게요.

(원본: `html_grammar.html`의 간단 정리)

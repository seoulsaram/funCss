### 미래에 도입될 css 소개

```js
💡 22.6월 현재 아직은 아래의 기능을 지원하는 브라우저가 없음에 주의!
```

[이 비디오를 보고 작성함](https://www.youtube.com/watch?v=kkiLBF_YerM&t=81s) <br/>
[이 글을 참조하여 작성함](https://ui.toast.com/weekly-pick/ko_20220603)

---

1. color-mix

- 명시한 컬러들을 섞어주는 기능.

```css
/* 자동으로 50%씩 섞어줌 */
background-color: color-mix(red, blue);

/* 섞을 퍼센테이지 명시 */
background-color: color-mix(red 30%, blue 70%);

/* 어떤 색 표준 사용할지 명시한 경우 */
background-color: color-mix(in srgb, #34c9eb 10%, white);
```

---

2. accent-color

- hover, focus, checked 등 특수한 상황의 포인트 컬러를 한 번에 명시 가능하다.

```css
:root {
  accent-color: pink;
}
```

---

3. color-contrast()

- 배경색 대비하여 잘 보이는 색을 직접 고르는 대신 브라우저가 적절한 색을 골라주는 기능.
- 디폴트 값으로는 흰색 또는 검정색을 제시해줌.

```css
/* 배경색 red에 알맞는 color제시 */
.box {
  background-color: red;
  color: color-contrast(red);
}

/* 세세한 설정 would be */
/* blue: 배경색 */
/* vs ~~ : 브라우저가 고를 수 있는 색상들 */
/* 이 경우 브라우저가 pink, yellow, green 중 선택 */
.box {
  color: color-contrast(blue vs pink, yellow, green);
}
```

---

4. inert

- `inert`는 css보다는 html 어트리뷰트.
- focus, click 등 유저와의 상호작용을 막을 때 유용하다.
- `inert`는 `disabled`와 같이 css적으로 변하진 않지만, `inert`에 css요소를 별도로 줄 수는 있다.
- 특정 html요소에만 사용할 수 있는 `readonly`, `disabled`와 달리 모든 html요소에 사용 가능하다.
- 크롬 브라우저 102버전부터 적용된다.

```js
💡 언제 유용한가?
- 요소가 DOM트리에 있으나 화면 밖에 있거나, 숨겨져 있는 경우
- 요소가 DOM트리에 있으나 상호작용 할 수 없도록 설정해야 하는 경우
유용하다.
예를 들어 버튼을 눌러야만 열리는 창이 있다고 할 때,
창이 닫혀있어도 tap버튼으로 해당 창 속에 있는 input이나 button요소에 접근할 수 있다.
이 때 창이 닫혀있는 경우 inert를 true로 준다면 이러한 인터렉션을 방지할 수 있다.
```

---

5. has()

- 부모 요소에 특정 자식이 있는지 여부에 따라 부모 요소의 스타일을 할 수 있음

```html
<form>
  <button></button>
</form>

<a href="#" />
<a href="#">
  <img src="" art="" />
</a>
<a href="#" />
```

```css
/* 버튼을 갖고있는 입력폼에 스타일 추가 */
form:has(button) {
  background-color: blue;
}

form:has(button:hover) {
  text-decoration: underline;
}

/* img태그를 갖고있는 a태그의 스타일 변경 */
a:has(> img) {
  color: red;
}
```

---

6. dvh, lvh, svh

- 윈도우 사이즈를 조절할 수 없는 mobile을 위한 프로퍼티들이다.
- dvh : dynamic viewport height
- lvh : largest viewport height
- svh : viewport height
- lvh는 상단의 navigation 없는 화면 크기
- svh는 상단의 nav가 있는 화면 크기
- dvh는 네비게이션이 표시되는지 여부에 따라 달라짐.

---

7. @nest

```css
/* nav안에 ul..nav안에 ul안에 ul.. */
nav {
}
nav ul {
}
nav ul li {
}

/* into this! */
nav {
  & ul {
    & li {
    }
  }
}
```

- 하지만 `@nest`를 사용하면 더 강력한 기능을 쓸 수 있음
- 참고로 `:not`선택자는 이미 지정된 css 스타일에서 특정한 요소를 제외시킬 경우 사용.

```css
/* This */
.foo {
  color: red;
  @nest: not(&) {
    color: blue;
  }
}
/* equals to this */
.foo {
  color: red;
}
:not(.foo) {
  color: blue;
}
```

---

8. @scope

- 스타일의 범위를 지정하거나 자신만의 버블로 지정할 수 있다.
- theme을 줄 때 유용하다.

```css
/* header안의 title/nav 스타일 지정 */
@scope (header) {
  .title {
    font-size: 36px;
  }
  nav {
    display: flex;
  }
}

/* aside안의 title/nav 스타일 지정 */
@scope (aside) {
  .title {
    font-size: 28px;
  }
  nav {
    display: grid;
  }
}
```

---

9. @container

- 반응형을 구현할 때 이젠 넓이 뿐만 아니라 그 부모 요소에 대응할 수 있다.

```css
header {
  container-type: inline-size;
  container-name: header-container;
}

/* header-container의 최소 너비가 600px일 때- */
@container header-container (min-width:600px) {
  nav {
    display: flex;
  }
}
```

---

10. custom-media

- 미디어 쿼리 변수를 만들고 재사용할 수 있다.

```js
💡 참고
- prefers-color-scheme는 사용자의 시스템 라이트 테마나 다크 테마를
사용하는지 탐지하는 데에 사용됨.
- light : 사용자가 시스템에 라이트 테마 사용을 선호하거나 선호하는 테마를 알리지 않았음을 나타냄.
- dark : 사용자가 시스템에 다크 테마 사용을 선호함을 알렸음을 나타냄.

- orientation : 가로모드/세로모드인지 판별. (portrait:세로 / landscape: 가로모드)
```

```css
@custom-media --darkMode (prefers-color-scheme: dark);
@custom-media --lightMode (prefers-color-scheme: light);
@custom-media --portrait (orientation: portrait);
@custom-media --iPhone (max-device-width: 480px);

/* 사용 시 */
@media (--darkMode) and(--portrait) {
  body {
    ...;
  }
}

@media (--lightMode) and(--portrait) and(--iPhone) {
  body {
    ...;
  }
}
```

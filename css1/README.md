```js
๐ก index.html๋ก open with live server๋ก ํ๋ฉด๊ณผ ํจ๊ป ํ์ธํ๋ฉด์ ๋ณด์ธ์.
```

---

1. transition์ผ๋ก step๋ณ ์์ง์ ํจ๊ณผ ์ฃผ๊ธฐ

```css
<div class='box' > </div > //
.box {
  width: 30px;
  height: 30px;
  background-color: grey;
}
.box:hover {
  background-color: hotpink;
  width: 120px;
  transition: all 1s 500ms steps(6);
  /* time ์ต์์ 2๊ฐ ์ฃผ๋ฉด ๋ค์ ์ค ์๊ฐ ๋ค์ transition์ด ๋จนํ
    500ms ๋ค์ 1์ด์ ๊ฑธ์ณ 6์คํ์ผ๋ก ํจ๊ณผ๊ฐ ๋ํ๋๋ค. */
}
```

---

2. ์ฌ์ด ํญ ๋์์ธ ๋ง๋ค๊ธฐ

```css
<h3 class='title' > Fun CSS</h3 > //
.title {
  padding: 0.2em 0.5em;
  margin-top: 0;
  border-left: 10px solid hotpink;
  background: lightblue;
}
```

---

3. ๊ธ์์ ๊ทธ๋ผ๋์ธํธ ๋ฃ๊ธฐ

```css
<h3 class='text-gradient' > Text Gradient</h3 > //

.text-gradient {
  margin-top: 0;
  background: linear-gradient(blue, red);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}
```

---

4. textarea ๋ฆฌ์ฌ์ด์ฆ none

```css
<textarea > </textarea > // 

textarea {
  resize: none;
}
```

---

5. ํ๋ฉด ์ฌ์ด์ฆ ๋์ด๊ฐ๋ ํ์คํธ๋ฅผ ์์์ ์ค๋ฐ๊ฟ

```css
<p class='wordWrap' > ํ๋ฉด ์ฌ์ด์ฆ ๋์ด๊ฐ๋ ํ์คํธ๋ฅผ ์์์ ์ค๋ฐ๊ฟ ํด์ฃผ๋ ์คํ์ผ. ํ๋ฉด์ ๋ฆฌ์ฌ์ด์ฆ ํด๋ณด์ธ์ฉ. ์ฉ์ฉ์ฉ </p > //

.wordWrap {
  word-wrap: break-word;
}
```

---

6. ๋ฌธ์์ด ์ฒซ๊ธ์๋ง ์คํ์ผ์ฃผ๊ธฐ + ์ฒซ๋ฒ์งธ ๋ผ์ธ๋ง ์คํ์ผ ์ฃผ๊ธฐ

- ํ๋ฉด์ด ์ข์์ ธ์ ์ค๋ฐ๊ฟ ๋๋ ๋๋ ๊ธ์๋ค์๋ ์คํ์ผ์ด ์ฌ๋ผ์ง.

```css
<p class='letter' > Bon's Fun CSSBon's Fun CSSBon's Fun CSSBon's Fun CSSBon's Fun CSSBon's Fun CSS</p > .letter::first-letter {
  font-size: 20px;
  font-weight: bold;
  color: royalblue !important;
}
.letter::first-line {
  color: pink;
}
```

---

7. ๊ธ์๋ฅผ ๋ฃ์ง ์์ ๋น div์๋ง ๋ฐ๋ก ์คํ์ผ์ ์ค ์ ์์.

```css
<div class='emptyBox' > not Empty</div > //
<div class='emptyBox' > </div> //
<div class='emptyBox' > not Empty</div > //

.emptyBox {
  background: saddlebrown;
  color: white;
  padding: 10px;
}
.emptyBox:empty {
  background: wheat;
}
```

---

8. firt-of-type ์ฐ์ต! content ๋ฐ์ pํ์์ ์ฒซ๋ฒ์งธ ์์ด์๊ฒ ์คํ์ผ์ฃผ๊ธฐ

```css
<div id="content"> //
    <h3>title</h3> //
    <p>aaa</p>     //
    <p>bbb</p>     //
    <p>ccc</p>     //
</div>//

#content p:first-of-type {
  color: violet;
}
```

---

9. text-shadow ์ฃผ๊ธฐ

```css
<p class="sd">Hello BON!</p> //

.sd {
  text-shadow: 5px 5px yellowgreen;
}
```

10. list ์คํ์ผ ํฌ์ง์ + ๋ง์ปค ์คํ์ผ

```css
<ul class="lsp"> //
  <li class="bg">list1</li> //
  <li class="bg">list2</li> //
  <li class="bg">list3</li> //
</ul> //

.bg {
  background: goldenrod;
}
.bg::marker {
  color: green;
}
.lsp {
  list-style-position: inside;
}
```

---

11. ๋ฌธ์ฅ ๋ค์ฌ์ฐ๊ธฐ

```css
<p class="ti">hi</p> ///
<p>my name is</p> ///
<p>someone</p> ///

.ti {
  text-indent: 10px;
}
```

---

12. ๊ธ์ ๋ค์ง๊ธฐ

```css
<p class="wm">ABC</p> //

.wm {
  writing-mode: vertical-lr;
}
```

---

13. zoom์ผ๋ก ์์ ํ๋ํ๊ธฐ

```css
<div class="zoom"></div>   //
<div class="zoom z"></div> //

.zoom {
  width: 50px;
  height: 50px;
  background: green;
  margin-bottom: 4px;
}
.z {
  zoom: 130%;
}
```

---

14. ์ ๋๋ฉ์ด์

```css
<h2 class="ani">WOW</h2> //
<hr />                  //
์๊น ์ฒด์ธ์ง ์ ๋๋ฉ์ด์        //
<div class="changeColor"></div> //

.ani {
  margin-top: 0;
  animation-duration: 3s;
  animation-name: slide;
}
@keyframes slide {
  from {
    margin-left: 100%;
  }
  to {
    margin-left: 0%;
  }
}

.changeColor {
  width: 50px;
  height: 50px;
  border: solid 1px;
  animation-duration: 3s;
  animation-name: changeCl;
}
@keyframes changeCl {
  0% {
    background: gold;
  }
  50% {
    background: black;
  }
  100% {
    background: lightcoral;
  }
}
```

---

15. scss์ extend๊ธฐ๋ฅ์ ์ฌ์ฉํ์ฌ ์คํ์ผ ์ฃผ๊ธฐ

```css
<div class="box1"></div> //
<div class="box2"></div> //
<div class="box3"></div> //

%t {
  width: 50px;
  height: 50px;
  border: 1px solid black;
  margin-bottom: 4px;
}

.box1 {
  @extend %t;
  background: blanchedalmond;
}

.box2 {
  @extend %t;
  background: cadetblue;
}
.box3 {
  @extend %t;
  background: chocolate;
}
```

---

16. @supports ์ฌ์ฉํด๋ณด๊ธฐ

- ๋ธ๋ผ์ฐ์ ๊ฐ display grid๋ฅผ supportํ๋์ง ์ ํ๋์ง์ ๋ฐ๋ผ
  ๊ฐ๊ธฐ ๋ค๋ฅธ ํจ๊ณผ๋ฅผ ์ค ์ ์๋ค!

```css
<div class="supports">  //
    <div></div>         //
    <div></div>         //
</div>                  //

.supports {
  div {
    width: 50px;
    height: 50px;
    margin-bottom: 4px;
    background: blueviolet;
  }
}
@supports (display: grid) {
  .supports {
    display: grid;
  }
}
@supports not (display: grid) {
  .supports {
    display: flex;
  }
}
```

---

17. scroll-snap-type ์ฌ์ฉํด๋ณด๊ธฐ

- ํ ํ๋ฉด์ ๊ฝ ์ฐจ๋ div๊ฐ ์ธ๋ก ๋๋ ๊ฐ๋ก๋ก ์ฌ๋ฌ๊ฐ ์์ ๋,
- ์คํฌ๋กค ํ์ ์ div๊ฐ ์๋ฆฌ์ง ์๊ณ  ๋ฐ๋ก ๋ค์ div๋ก ๊น๋ํ๊ฒ ์คํฌ๋กค๋ง ๋๋๋ก ํ๋ ๊ธฐ๋ฅ.

- key point๋ ๋ถ๋ชจ ์์์ `scroll-snap-type` ์, ์์ ์์์ `scroll-snap-align` ๋ฅผ ์ค์ ํด์ฃผ๋ ๊ฒ.

```css
<div class="scroll-container">            //
    <div class="item scroll-area">1</div> //
    <div class="item scroll-area">2</div> //
    <div class="item scroll-area">3</div> //
    <div class="item scroll-area">4</div> //
    <div class="item scroll-area">5</div> //
    <div class="item scroll-area">6</div> //
    <div class="item scroll-area">7</div> //
    <div class="item scroll-area">8</div> //
</div>                                    //

.scroll-container,
.scroll-area {
  width: 150px;
  height: 150px;
}
.scroll-container {
  overflow: auto;
  /* ADD THIS TO THE PARENT */
  scroll-snap-type: y mandatory;
}
.item {
  /* ADD THIS TO THE CHILD */
  scroll-snap-align: center;
  display: inline-block;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 38px;
}

.item:nth-child(odd) {
  background: chocolate;
}
.item:nth-child(even) {
  background: cornflowerblue;
}
```

---

18. is seudo selector ์ฌ์ฉํด๋ณด๊ธฐ

- ์ ํ์๋ฅผ ๊น๋ํ๊ฒ ์์ฑํ๋ ๋ฐฉ๋ฒ.

```css
<header>                //
    <nav>               //
    <button></button>   //
    </nav>              //
    <button></button>   //
</header>               //

/* ์ด ์ฝ๋๋ฅผ :is๋ฅผ ์ฌ์ฉํด ๋ ๊น๋ํ๊ฒ ์์ฑํ๋ฉด */
header button,
nav button {
  width: 60px;
  height: 20px;
  background-color: tomato;
}

/* ์ด๋ ๊ฒ ํ  ์ ์๋ค! */
/* header, nav์์ด? ๊ทธ๋ผ ๊ทธ ๋ฐ์ button ์ ํํ ๊ฒ */
:is(header, nav) button {
  width: 60px;
  height: 20px;
  background-color: tomato;
}
```

---

19. ์ด๋ฏธ์ง๋ ๋น๋์ค์ ๋น์จ์ ์ ํ  ์ ์๋ aspect-ratio ์ฌ์ฉํด๋ณด๊ธฐ

```css
<img class="exp" src="./example.jpeg" alt="" /> //

.exp {
  width: 100px;
  aspect-ratio: 16 / 9;
  // aspect-ratio: 1 / 1; /* width and height are equal proportion */
  // aspect-ratio: 2 / 1; /* width is twice the height*/
  // aspect-ratio: 1 / 2; /* width is half the height */
  // aspect-ratio: 16 / 9  /* typical video aspect ratio */
  // aspect-ratio: auto 4 / 3; /* width:height, unless it's a replaced element */
}
```

---

20. sticky ํ์ฉํด์ ์ ์ ์ ์คํฌ๋กค์ ๋ฐ๋ผ๋ค๋๋ header ๋ง๋ค๊ธฐ

```css
<div id="container2">      //
  <section>                //
    <aside>Header</aside>  //
  </section>               //
  <section>                //
    <aside>Header</aside>  //
  </section>               //
  <section>                //
    <aside>Header</aside>  //
  </section>               //
  <section>                //
    <aside>Header</aside>  //
  </section>               //
</div>                     //

#container2 {
  width: 150px;
  height: 400px;
  overflow: auto;
  section {
    background-color: tomato;
    /* 2. ์ ์๋ ๋์ด๊ฐ ์๋ ์ปจํ์ด๋ ์์ ๊ทธ ์์๋ฅผ ๋ฃ์ผ๋ฉด ๋๋ค! */
    height: 70%;
    width: 100%;
    margin: 35px 0px;
    display: flex;
    justify-content: flex-end;
  }
  aside {
    background-color: teal;
    height: 50px;
    width: 100%;
    /* 1. ์ํ๋ ์์์ position sticky๋ฅผ ๋ฃ๊ณ  */
    position: sticky;
    top: 0px;
    text-align: center;
    color: white;
    display: flex;
    align-items: center;
    justify-content: center;
  }
}
```

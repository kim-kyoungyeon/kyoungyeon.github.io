### ๐ DOM ์ด๋?
๋ฌธ์ + ๊ฐ์ฒด์งํฅ
html xml ๋ฌธ์ํ๋ก๊ทธ๋๋ฐ
๋ฐ์ดํฐ ํ์๊ณผ ๊ด๋ จ ๊น์ด๋ณด์.
### ๐ HTML์ JavaScript ์ ์ฉํ๋ ค๋ฉด ?

`<script>` ํ๊ทธ๋ฅผ ์ด์ฉํฉ๋๋ค
![](https://velog.velcdn.com/images/ww3ysq/post/6fe7acb6-ba74-41d5-b714-e96e42fb42b7/image.png)

_์น ๋ธ๋ผ์ฐ์ ๊ฐ ์์ฑ๋ ์ฝ๋๋ฅผ ํด์ํ๋ ๊ณผ์ ์์ `<script>` ์์๋ฅผ ๋ง๋๋ฉด, ์น ๋ธ๋ผ์ฐ์ ๋ HTML ํด์์ ์ ์ ๋ฉ์ถฅ๋๋ค. ( HTML ํด์์ ์ ์ ๋ฉ์ถ ์น ๋ธ๋ผ์ฐ์ ๋ `<script>` ์์๋ฅผ ๋จผ์  ์คํํฉ๋๋ค. `<script>` ์์๋ ๋ฑ์ฅ๊ณผ ํจ๊ป ์คํ๋๋ค๋ ์ฌ์ค์ ๊ผญ ๊ธฐ์ตํ์ธ์._

### ๐ `<span>ํ๊ทธ ์ฌ์ฉ๋ฒ`

| ํ๊ทธ |       ์์ฑ       |      ๋น๊ณ        |
| :--: | :--------------: | :-------------: |
| span |     display      | diplay์์ ๋ณ๊ฒฝ |
|      |      width       |    ๊ฐ๋กํฌ๊ธฐ     |
|      |      height      |    ์ธ๋กํฌ๊ธฐ     |
|      | background-color |   ๋ฐฐ๊ฒฝ์ ๋ณ๊ฒฝ   |
|      |      color       |  ๊ธ์ ์ ๋ณ๊ฒฝ   |
|      |    font-style    | ๊ธ์ ํ์ ๋ณ๊ฒฝ  |
|      |      margin      |  ์ธ๋ถ ์ฌ๋ฐฑ์ค์   |
|      |     padding      |  ๋ด๋ถ ์ฌ๋ฐฑ์ค์   |
|      |      border      |   ํ๋๋ฆฌ ์ค์    |

1. display๋ <span>ํ๊ทธ์ ์์๋ฅผ ๋ณ๊ฒฝํ  ์ ์๋ ์์ฑ์๋๋ค. <span>ํ๊ทธ์ display์์ฑ defalut๊ฐ์ inline์ผ๋ก ๋์ด์์ต๋๋ค.

2. width๋ <span>ํ๊ทธ์ ๊ฐ๋ก ์ฌ์ด์ฆ๋ฅผ ์ง์ ํด์ค ์ ์๋ ์์ฑ์๋๋ค. ์ด ์์ฑ์ ์ฌ์ฉํ๊ธฐ ์ํด์๋ display์์ฑ๊ฐ์ inline์์ block์ผ๋ก ๋ฐ๊ฟ์ค์ผํฉ๋๋ค.

3. height๋ <span>ํ๊ทธ์ ์ธ๋ก ์ฌ์ด์ฆ๋ฅผ ๋ณ๊ฒฝ์ํฌ ์ ์๋ ์์ฑ์๋๋ค. ์ด ์์ฑ์ ์ฌ์ฉํ๊ธฐ ์ํด์๋ display์์ฑ๊ฐ์ด inline์ผ ๊ฒฝ์ฐ์๋ ์ ์ฉ๋์ง ์์ต๋๋ค.

4. background-color๋ <span>ํ๊ทธ์ ๋ฐฐ๊ฒฝ์์ ์ง์ ํด์ค ์ ์๋ ์์ฑ์๋๋ค.

5. color๋ <span>ํ๊ทธ์์์๋ ๊ธ์์ ์์์ ์ง์ ํด์ฃผ๋ ์์ฑ์๋๋ค.

6. font-style๋ <span>ํ๊ทธ์์ ๊ธ์ ํ์์ ์ง์ ํด์ฃผ๋ ์์ฑ์๋๋ค.

7. margin <span>ํ๊ทธ์ ๋ ์ด์์๊ฐ์ ์ฌ๋ฐฑ(์ธ๋ถ์ฌ๋ฐฑ)์ ์ง์ ํด์ฃผ๋ ์์ฑ์๋๋ค.

8. padding <span>ํ๊ทธ์ ๋ด๋ถ์ฌ๋ฐฑ์ ์ง์ ํด์ฃผ๋ ์์ฑ์๋๋ค.

9. border <span>ํ๊ทธ ์ธ๊ณฝ์ ํ๋๋ฆฌ๋ฅผ ์ค ์ ์๋ ์์ฑ์๋๋ค.

### ๐ DOM ๊ตฌ์กฐ

_body๊ฐ ๊ฐ์ฅ ์์์ ์๊ณ , ์๋์ ์ฌ๋ฌ ๊ตฌ์ฑ์์๊ฐ ๋ถ๋ชจ-์์ ๊ด๊ณ๋ฅผ ๊ฐ์ง๊ณ  ์์ต๋๋ค. ์ด ๊ด๊ณ๋ฅผ ๊ทธ๋ ค๋ณด๋ฉด ์๋์ ๋น์ทํ ๊ตฌ์กฐ๊ฐ ๋ง๋ค์ด์ง๋๋ค._

![](https://velog.velcdn.com/images/ww3ysq/post/a1a7b299-f020-4095-aae1-5f41bb81114c/image.png)

```jsx
html>
  <body> //๋ถ๋ชจ
    <div id="nav"> //์์ ์๋ฆฌ๋จผํธ
      <div class="logo"></div>
      <div class="menu-wrapper">
        <div class="menu">menu</div>
        <div class="menu">menu</div>
        <div class="menu">menu</div>
        <div class="profile-photo">photo</div>
      </div>
    </div>
    <div id="news-contents"> //์์ ์๋ฆฌ๋จผํธ
      <div class="news-content-wrapper">
        <div class="news-picture">news-picture</div>
        <div class="news-title">news-title</div>
        <div class="news-description">news-description</div>
      </div>
    </div>
    <div id="footer">footer</div> //์์ ์๋ฆฌ๋จผํธ
  </body>
</html>

```

์ค๋ช :
ํธ๋ฆฌ ๊ตฌ์กฐ๋ผ๊ณ  ํฉ๋๋ค. ํธ๋ฆฌ ๊ตฌ์กฐ์ ๊ฐ์ฅ ํฐ ํน์ง์ ๋ถ๋ชจ๊ฐ ์์์ ์ฌ๋ฌ ๊ฐ ๊ฐ์ง๊ณ , ๋ถ๋ชจ๊ฐ ํ๋์ธ ๊ตฌ์กฐ๊ฐ ๋ฐ๋ณต๋๋ ์ ์๋๋ค. ์ฆ, ๋ถ๋ชจ๊ฐ ๊ฐ์ง ํ๋ ๋๋ ์ฌ๋ฌ ๊ฐ์ ์์ ์๋ฆฌ๋จผํธ๋ฅผ ์กฐํํ๋ ์ฝ๋๋ฅผ ์์ฑํ๋ค๋ฉด, ์ฌ๋ฌ ๋ฒ ๋ฐ๋ณตํด์ ์คํํ๋ ์ฝ๋๊ฐ ํ์ํฉ๋๋ค.

```jsx
consoel.log(document.body);
consoel.dir(document.body);
consoel.dir(document.body.children[1]);
// document.body.children ์ ์ฒซ ๋ฒ์งธ ์๋ฆฌ๋จผํธ๋ฅผ ์กฐํ
```

### ๐ v8 ์์ง?

- ์๋ฐ์คํฌ๋ฆฝํธ ์์ง?
  ์๋ฐ์คํฌ๋ฆฝํธ ์ฝ๋๋ฅผ ์คํํ๋ ํ๋ก๊ทธ๋จ์ผ๋ก, ์๋ฐ์คํฌ๋ฆฝํธ ์ฝ๋๋ฅผ ๋ง์ดํฌ๋กํ๋ก์ธ์๊ฐ ์ดํดํ  ์ ์๊ฒ ๋ ๋ฎ์ ์์ค์ ์ธ์ด(๊ธฐ๊ณ์ด)๋ก ๋ณํํด์ฃผ๋ ๊ฒ์ด๋ค.
- v8 ์์ง์ ์ฐ๊ฒ๋ ๊ณ๊ธฐ?
  ๋ค๋ฅธ ์๋ฐ์คํฌ๋ฆฝํธ ์์ง์ ์น ํน์ฑ์ ์ ์ ์ ์ํธ์์ฉ์ ์ํด ์ฆ์์ฑ์ด ์๋ ์ธํฐํ๋ฆฌํฐ ๋ฐฉ์์ ์ฌ์ฉํ๋๋ฐ, ์ด๋ ์ฝ๋๊ฐ ๋ง์์ง์๋ก ์๋๊ฐ ๋๋ ค์ง๋ค๋ ๋จ์ ์ด ์๊ธฐ๋๋ฌธ์ ์ด ์ ์ ๋ณด์ํด์ ์๋ฐ์คํฌ๋ฆฝํธ ์ฝ๋๋ฅผ ์ข ๋ ํจ์จ์ ์ผ๋ก ๋ฒ์ญํ๋ V8 ์์ง์ด ๋์ค๊ฒ ๋์๋ค.
- ํน์ง
  Google Chrome, Node.js์์ ์ฃผ๋ก ์ฌ์ฉํ๋ค
  ์คํ์์ค๊ฐ ECMAScript ๊ท๊ฒฉ์ C++๋ก ์์ฑ๋์ด์๋ค
  ํด๋ผ์ด์ธํธ(Chrome)์ ์๋ฒ(Node.js)์ธก ์ ํ๋ฆฌ์ผ์ด์์ ๋ชจ๋ ์ฌ์ฉํ๋ค

### ๐ JavaScript Engine AST

_JavaScript๋ ์ธํฐํ๋ฆฌํฐ ๋๋ ๊ณผ์ ์ ๊ฑฐ์น๊ธฐ ์ ์, ํด๋น ์์ค์ฝ๋๋ฅผ parser -> Abstract Syntax Tree ํํ๋ก ๋ฐ๊พธ๊ฒ ๋ฉ๋๋ค._

![](https://velog.velcdn.com/images/ww3ysq/post/e5c7d77a-ca5d-49d7-a8a3-85c1935a8830/image.png)

### ๐ ์๋ฐ์คํฌ๋ฆฝํธ & ์ด์๋ธ๋ฆฌ ์์ง

![](https://velog.velcdn.com/images/ww3ysq/post/d97d3845-ddfb-41e6-89f8-593c6cd61841/image.png)

- ์์ (์ธํฐํ๋ฆฌํฐ + ์ปดํ์ผ๋ฌ)
  1 ์์ค ์ฝ๋๋ฅผ ๊ฐ์ ธ์์ ๊ฐ์ฅ ๋จผ์  ํ์(Parser)์๊ฒ ๋๊ธด๋ค.
  2 ์์ค ์ฝ๋๋ฅผ ๋ถ์ํ ํ AST(Abstract Syntax Tree), ์ถ์ ๊ตฌ๋ฌธ ํธ๋ฆฌ๋ก ๋ณํํ๊ฒ ๋๋ค.
  3 AST๋ฅผ ๊ทธ๋ฆผ์ ๋์์๋ Ignition์๊ฒ ๋๊ธฐ๋๋ฐ ์ด ์น๊ตฌ๋ ์๋ฐ์คํฌ๋ฆฝํธ๋ฅผ ๋ฐ์ดํธ ์ฝ๋(Bytecode)๋ก ๋ณํํ๋ ์ธํฐํ๋ฆฌํฐ์ด๋ค

` ์ธํฐํ๋ฆฌํฐ - ์ฝ๋๊ฐ ์คํ์ ์ค๋จ์๋ก ์ฐจ๋ก๋ก ์คํํด์ ํ์ค์ฝ๊ณ  ์คํํ๋ ๋ฐฉ์์ผ๋ก, ๋์ผํ ๋์์ํ๋ ํจ์๊ฐ ์ฌ๋ฌ๋ฒ ๋์ค๋๋ผ๋ ์ด๋ฅผ ์ปดํ์ผ ํ๋ ๊ณผ์ ์ ๊ฑฐ์น๊ฒ ๋ฉ๋๋ค. ๋ฐ๋ผ์ ์ด๋ ๋งค์ฐ ๋นํจ์จ์ ์ด๋ค`

Q ์ ์ธํฐํ๋ฆฌํฐ๋ฅผ ์ฐ๋์?
์๋ณธ ์์ค ์ฝ๋๋ณด๋ค ์ปดํจํฐ๊ฐ ํด์ํ๊ธฐ ์ฌ์ด ๋ฐ์ดํธ ์ฝ๋๋ก ๋ณํํจ์ผ๋ก์จ ์๋ณธ ์ฝ๋๋ฅผ ๋ค์ ํ์ฑ(Parsing)ํด์ผํ๋ ์๊ณ ๋ฅผ ๋๊ณ  ์ฝ๋์ ์๋ ์ค์ด๋ฉด์ ์ฝ๋ ์คํ ๋ ์ฐจ์งํ๋ ๋ฉ๋ชจ๋ฆฌ ๊ณต๊ฐ์ ์๋ผ๋ ค๋ ๊ฒ์ด๋ค.

4 ๋ฐ์ดํธ ์ฝ๋๋ฅผ ์คํํจ์ผ๋ก์จ ์ฐ๋ฆฌ์ ์์ค ์ฝ๋๊ฐ ์ค์ ๋ก ์๋ํ๊ฒ ๋๋ค
5 ์์ฃผ ์ฌ์ฉ๋๋ ์ฝ๋๋ TurboFan์ผ๋ก ๋ณด๋ด์ ธ์ Optimized Machine Code, ์ฆ ์ต์ ํ๋ ์ฝ๋๋ก ๋ค์ ์ปดํ์ผ๋๋ค.
6 ์ฌ์ฉ์ด ๋ ๋๋ค ์ถ์ผ๋ฉด Deoptimizing ํ๊ธฐ๋ ํ๋ค.

## โ Advanced Challenge

- CreateDocumentFragment๋ฅผ ํ์ฉํ์ฌ, ๋ ํจ์จ์ ์ผ๋ก DOM์ ์ ์ดํ๋ ๋ฐฉ๋ฒ
- HTML5 template tag ์ฌ์ฉ๋ฒ์ ์ดํดํ  ์ ์๋ค.
- element์ node์ ์ฐจ์ด๋ฅผ ์ดํดํ  ์ ์๋ค.
- children๊ณผ childNodes์ ์ฐจ์ด๋ฅผ ์ดํดํ  ์ ์๋ค.
- remove์ removeChild์ ์ฐจ์ด๋ฅผ ์ดํดํ  ์ ์๋ค.
- ๊ฐ์ ์๋ฆฌ๋จผํธ๋ฅผ appendChild ํ๋ฉด, ๊ธฐ์กด ์๋ฆฌ๋จผํธ๋ฅผ ๋ณต์ฌํ ๊น?
- ์ขํ ์ ๋ณด ์กฐํ๋ฅผ ํ  ์ ์๋ค. - offsetTop...
- ํฌ๊ธฐ ์ ๋ณด ์กฐํ๋ฅผ ํ  ์ ์๋ค. - offsetWidth...

* ํ๋ก์ ํธ์์ ์ด react-router-dom
* virtual Dom ๊ฐ๋ ๊ณต๋ถ

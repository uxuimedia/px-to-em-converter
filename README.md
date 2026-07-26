# Конвертер (калькулятор) перевода PX в EM и обратно (px-to-em-converter)

![Конвертер PX в EM](./images/px-to-em.jpg)

Конвертер (калькулятор) перевода PX в EM и обратно. Расчет производится на основе выбранного вами размера базового шрифта в пикселях. Удобный ковертер для фронтенд-разработчиков и дизайнеров.

[ДЕМО](https://uxuimedia.github.io/tools/px-to-em/)

## HTML

```html
<div class="container-px-em">    
  <div class="basefont">
    <p>basefont:</p><input type="text" class="chosen" value="16" placeholder="16">px</div>
  <div class="px-em">
    <div class="px"><input type="text" class="input px-input" placeholder="0" />
      <div class="text">px</div>
    </div>
    <div class="em"><input type="text" class="input em-input" placeholder="0" />
      <div class="text">em</div>
    </div>
  </div>
</div>
```

## JavaScript

```js
var px = document.querySelector(".px-input");
var em = document.querySelector(".em-input");
var bf = document.querySelector(".chosen");
var pxValue = px.value;
var basefont = bf.value;
px.addEventListener("keyup", function() {
  basefont = bf.value;
  pxValue = px.value;
  calculatePXtoEM(pxValue, basefont);
});

em.addEventListener("keyup", function() {
  basefont = bf.value;
  emValue = em.value;
  calculateEMtoPX(emValue, basefont);
});

function calculatePXtoEM(givenPx, basefont) {
  console.log(givenPx);
  if (basefont === "") {
    basefont = 16;
  }
  var returnEm = givenPx / basefont;
  em.value = returnEm;
}

function calculateEMtoPX(givenEm, basefont) {
  console.log(givenEm);
  if (basefont === "") {
    basefont = 16;
  }
  var returnPx = givenEm * basefont;
  px.value = returnPx;
}
```

## CSS

```css
/* px to em */
.container-px-em {
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
.container-px-em h1 {
  font-size: 5.85rem;
  padding: 0 0 0.2em 0;
  margin: 0;
}
.container-px-em .input {
  border-top: none;
  border-left: none;
  border-right: none;
  padding-top: 0.4em;
  border-bottom: 1px dotted #000;
  outline: 0;
  width: 150px;
  font-size: 3rem;
  text-align: right;
  margin-right: 0.3em;
  background-color: #ff90b3;
  outline: 0;
}
.container-px-em .input::-webkit-input-placeholder {
  color: #000;
  opacity: 0.2;
}
.container-px-em .px-em {
  display: flex;
}
.container-px-em .em,
.container-px-em .px {
  font-size: 2rem;
  display: flex;
  justify-content: flex-end;
  align-items: flex-end;
}
.container-px-em .em .text,
.container-px-em .px .text {
  padding-bottom: 0.2em;
}
.container-px-em .em {
  margin-left: 1em;
}
.container-px-em .em .text {
  margin-right: -0.3em;
}
.container-px-em .px-input {
  width: 95px;
}
.container-px-em .basefont {
  display: flex;
  align-items: baseline;
  font-size: 3.3rem;
  padding: 0 0 0.2em 0;
  margin: 0;
  border-bottom: 1px solid transparent;
}
.container-px-em .basefont p {
  margin: 0;
  padding: 0;
}
.container-px-em .basefont .chosen {
  width: 80px;
  border-top: none;
  border-right: none;
  border-left: none;
  margin-left: 0.2em;
  margin-right: 0.2em;
  font-size: 3.3rem;
  text-align: center;
  border-bottom: 2px dotted #000;
  background-color: #ff90b3;
  outline: 0;
}
.container-px-em .basefont .chosen::-webkit-input-placeholder {
  color: #000;
  opacity: 0.2;
}
/* end px to em*/
```

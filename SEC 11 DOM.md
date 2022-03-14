## Adding Javascript to Websites

- 在html tag裡設定`onload`attribute(建議是不要...)
- 在`<body></body>`後加上`<script></script>`，在裡面寫（也建議不要）
- `<script></script>`裡引用外部js，Good

```html
<script src="somescript.js"></script>
```

js、css擺放的順序也很有關係，如果先把js擺最前面，就會先做完裡面的內容再渲染css

而且放在`<body></body>`前面dom也存取不到html tag。通常把js擺在最底部，先讓整體網頁跑完，再來執行js

## Introduction to the Document Object Model (DOM)

以樹狀節點觀念展開html架構，並可以用JS對HTML進行操作、改變

- HTML Tree Generator: chrome套件

- Attributes: Attributes是我們寫在HTML的屬性，像是`<div type = 'text'>`。
- Properties: Properties是存在在DOM objects中的屬性，像是div.type。

當element有符合標準的的attribute時，相對應的property就會生成。但是當element不符合標準時，相對應的property就不會生成

Properties: `innerHTML`, `style`
Methods: `click()`, `appendChild()`

```html
<p id="foo">hello world</p>

<script>
    var foo = document.getElementById('foo');

    // 將背景顏色改為紅色
    foo.style['background-color'] = '#f00';

    // 將 margin-top 設為 100px
    foo.style.marginTop = '100px';
</script>
```


```html
<p id="foo">hello world</p>

<script>
    var foo = document.getElementById('foo');

    // 輸出 "" 空字串，因為 foo 上沒有設定 style 屬性
    alert(foo.style.cssText);

    // 將 foo 的字體大小設為 20px、字體顏色設為紫色
    foo.style.cssText = 'font-size: 20px; color: purple;';

    // 輸出 font-size: 20px; color: purple;
    alert(foo.style.cssText);
</script>
```


## Selecting HTML Elements with Javascript

- `document.getElementById('idName')`
  - ID是unique，只會有一個
- `document.getElementsBytagName('tag')`
  - HTMLCollection
- `document.getElementsByClassName('className')`
  - HTMLCollection

直接用css selector找

`document.querySelector('h1')`
`document.querySelector('li a')`
`document.querySelector('#id')`
`document.querySelector('.class')`

- `document.querySelector('selector')`
  - 利用 selector 來找尋 DOM 中的元素，並回傳相對應的第一個 element 
- `document.querySelectorAll('selector')`
  - 利用 selector 來找尋 DOM 中的所有元素，並回傳相對應的第一個 element ，集合為 NodeList

HTMLCollection
集合內元素為 HTML element ，也因此 Node type 只能接受 Element

NodeList
集合內元素為 Node ，也因此全部的 Node 都可以存放在 NodeLists內


```js
document.querySelector('.list a').style.color = 'green'
```
找出`.list`下面的`a`把顏色改成綠色

## Manipulating and Changing Styles of HTML Elements with JS

[HTML DOM Style Object](https://www.w3schools.com/jsref/dom_obj_style.asp)

通常在DOM裡面的property都跟css一樣，但會改成駝峰命名

```js
document.querySelector('button').style.backgroundColor='yellow'
```

## The Separation of Concerns: Structure vs Style vs Behaviour

css該做的事情是定義style，直接由js來操作css的屬性不太好

所以可以先在css裡先定義class內的屬性，藉由js來「加上class」，達到到切換style的效果

```js
// div is an object reference to a <div> element with class="foo bar"
div.classList.remove("foo");
div.classList.add("anotherclass");

// if visible is set remove it, otherwise add it
div.classList.toggle("visible");

//  add/remove visible, depending on test conditional, i less than 10
div.classList.toggle("visible", i < 10 );

alert(div.classList.contains("foo"));

div.classList.add("foo","bar"); //add multiple classes
```

## Text Manipulation and the Text Content Property

`innerHTML`: `<storng>hi</strong>`

`textContent`: `hi`

## Manipulating HTML Element Attributes

```js
document.querySelector("a").attribute;
document.querySelector("a").getAttribute("href");
document.querySelector("a").setAttribute("href","https://www.yahoo.com");
```
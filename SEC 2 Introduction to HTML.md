# Introduction to HTML

## Introduction to HTML
- HTML = HyperText Markup Language
- HTML是網頁的結構與骨幹
- HTML, XML, GML有著共通的歷史
[Codepen, 可以直接在線上測試HTML測試HTML,CSS, JS](https://codepen.io/)

```html
<h1> Hello </h1>
<!-- 
h1: tag name
<h1>: open tag
</h1>: close tag
利用open, close tag把內容包住
-->
```
- 標題標籤可從h1(最大)至h6(最小)
- 正確從Google找到資訊很重要
- `HTML MDN`, `w3 school`, `devdocs.io`可找到許多文件說明
- HTML不像word可以這麼簡單增加空白，必須用`<br>`，而且不需要open close tag，可任意使用放置

## The Anatomy of an HTML Tag
- 文件中，從tag omission可判別是否需要close tag
>如何查tag omission? devdocs.io!

- `<br>`, `<hr>`都不需要close tag(self-closing)
- 在瀏覽器畫面中右鍵Inspect，就會打開開發者模式，查看原始碼

```html
<hr size='3' align='center'>
<!-- 
hr: HTML element
size='3': HTML attribute   
attribute給定更多參數進行自定義, 用空格隔開
-->
```
>如何查HTML attribute ? devdocs.io!
- 常見attribute: `align`,`noshade`,`size`, `color`...等

課程範例
```html
<center>
    <hr size='3' align='left'>
    <h1>HELLO</h1>
    <br>
    <h3>豬油骨拿來滷</h3>
    <hr size='3' align='left'>
</center>
```

## What we're building - HTML Personal Site

[Wayback Machine: 各大網站的時光機](https://archive.org/web/)

- 早期的yahoo也只是由簡單的pure HTML所構成
- [但其實很多CS教授的個人網頁也是如此](https://www.cs.dartmouth.edu/~thc/)

## What is The HTML Boilerplate?

- 多多利用shortcut
- [前端開發神器 Emmet 快速上手教學整理，減少 HTML / CSS 輸入的麻煩](https://www.wfublog.com/2017/08/emmet-sublime-text.html)
- 在編輯器(例如VSC)輸入html，自動會偵測並顯示使用者想代入的Boilerplate(樣板)如下:

```html
<!DOCTYPE html>
<!--
告訴瀏覽器使用哪個html版本 html5
html4會很長一大串, html5簡化很多
-->
<html lang="en">
<head>
    <meta charset="UTF-8">
    <!--
    告訴瀏覽器使用UTF-8編碼
    UTF-8已經可以涵蓋許多語言字符
    -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
</body>
</html>

<!--
<html></html>: 告訴瀏覽器這段包的都是html
<head></head>: 頁面的基本資訊, 例如標題
<meta name='descripton' content='hi'>: 搜尋結果的摘要
-->
```

## How to Structure Text in HTML
- 正確的縮牌可以大幅增加程式碼可讀性
- 可以安裝beautify插件來排版
- `<em></em>`會比`<i></i>`來得好，因為HTML強調的是結構，而非定義樣式的風格
- `<b></b>`與`<strong></strong>`同理

## HTML Lists

- 無排序列表
```html
<ul>
    <li>this is list</li>
    <li>this is list</li>
</ul>
```
- 有排序列表
```html
<ol>
    <li>this is list</li>
    <li>this is list</li>
</ol>
```
- 排序列表也可以使用羅馬數字，或從特定數字起始[詳見連結](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol)

## HTML Image Elements

```html
<img src="src" alt="my pic">
```
img tag裡的alt也可能會影響SEO

- 可使用photobucket作為圖床
- src可以直接使用網路來源，也可以讀取資料夾底下的圖片
- crop-circle.imageonline.co

## HTML Links and Anchor Tags

```html
<a herf='www.notion.so'> 這是notion </a>
```
- 連結可以是網路的超連結，也可以是同資料夾底下的其他html檔
## What Are Favicons?

- "我的最愛"會出現的icon，也會出現在分頁
- go [favicon.cc](https://www.favicon.cc/)
- go [formito](https://formito.com/tools/favicon)


```html
<link rel="icon" href="favicon.ico">
```

##  HTML Divs

- `div`是html tag，用於把不同內容切塊分隔開來的「容器」，實際上不會對裡面的內容作出任何的變化，要靠css對不同的div進行定義
- 小補充: `body`, `h1`預設都會有margin


## The Box Model of Website Styling

![](/img/26.png)

- content: 本身裡面的內容
- padding: content跟boarder之間的空白
- border: 邊框
- margin: 整個element與其他element之間相鄰的距離
- 整個box的大小都會由這四個零件所決定

- `border-witdh`
- `padding`
- `margin`

### 課堂小測試

![](/img/0.png)

```html
<body>
    <div class="top-container"></div>
    <div class="middle-container"></div>
    <div class="bottom-container"></div>    
</body>
```

```css
.top-container { 
    background-color: aquamarine;
    border: solid;
    border-width: 10px;
    margin: 0px;
    padding: 20px;
    width:200px;
    height:200px;
}

.middle-container {
    background-color: red;
    border: solid;
    border-width: 20px;
    margin-left: 260px;
    width:200px;
    height:200px;

}

.bottom-container {
    background-color: yellow;
    border: solid;
    border-width: 10px;
    margin-left: 500px;
    width:200px;
    height:200px;
}
```

## CSS Display Property

- 四種property
  - block
  - inline
  - inline-block
  - none

- block property會佔據所有的寬度，例如
  - paragraph
  - header
  - list and item
  - form

因為paragraph帶有block特性，如果想對"pro"定義css（例如畫底線），用兩個`p`會被拆成兩行，這時就要用`span`來包

```html
<p>pro</p>
<p>grammer</p>
```

```html
<p><span>pro</span>grammer</p>
```
- `span`是一種 inline element，其他常見的有`a`、`img`，不能改變`width`(只能隨內容而變)
- 但是element都可以從css定義`display`讓html tag變為inline
- inline-block則是結合兩者屬性，能有width
- `display: none`會讓內容整個bang不見，好像不存在一樣
- 但`visibility:hidden`會隱藏內容，但還是保有位置
- inline-block、inline能實現橫向排版


## CSS Static and Relative

- 呈現的規則
  - content is everything: content會先決定width & height
  - order comes from code: 順序由code flow決定
  - Children sit on parent: div裡面的物件會比div還要在前(z axis) 
- position
  - `position:static`: default, 
  - `position:relative`: 從原本的位置移動相對距離，且不會影響到其他element原本位置
  - `position:absolute`
  - `position:fixed`

![](/img/1.png)



```css
img {
    position: relative;
    top: 50px;
} 
/*圖片會從原本的位置, "從上"被移動20px*/
```

## Absolute positioning

![](/img/3.png)

![](/img/2.png)

- relative: 從原本位置右邊出發往左推
- absolute: 從parent的右邊界出發往左推(parent的position要設定為relative，不然預設為`body`
- parent的position要設定為relative，不然預設為`body`
- parent的position要設定為relative，不然預設為`body`
- parent的position要設定為relative，不然預設為`body`

### 課堂練習

![](/img/4.png)

```html
<body>
<div class='red'></div>  
<div class='blue'></div>  
<div class='yellow'></div>  
</body>
```

```css
body{
  margin:0
}

.red {
  width: 100px;
  height: 100px;
  background-color: red;
  position: absolute;
  top:200px;
  left:200px;
}

.yellow {
  width: 100px;
  height: 100px;
  background-color: yellow;
  position: absolute;
}

.blue {
  width: 100px;
  height: 100px;
  background-color: blue;
  position: absolute;
  top:100px;
  left:100px;
}
```

### fixed

像凍結窗格，捲動視窗還是會停留在那

## The Dark Art of Centering Elements with CSS

- `text-align:center`: 文字、圖片置中(行內物件)
- `margin:0 auto`: 區塊(div)置中

```css
body {
   marging: 0;
   text-align: center; 
}

h1 {
  witdth : 10%
  margin: 0 auto;
  /*左右的margin自動調配*/
}
```

## Font Styling in Our Personal Site

- serif: 襯線 
- sans-serif: 非襯線
- 就像黑體vs新細明體


```css
body {
    text-align: center;
    margin: 0;
    font-family: Arial, Helvetica, sans-serif;
}

/*優先順序 Arial, Helvetica, sans-serif(任何非襯線); */
```

- web safe font: 最通用的幾種字體，避免過度使用者因為缺少字體而導致瀏覽體驗不佳
- [cssfontstack](https://www.cssfontstack.com/)
- 內含fallback，ex: 
- 想要更統一、更具風格: [google fonts embeddings](https://fonts.google.com/)

選了喜歡的字體，就可以套用link

![](/img/5.png)



## Adding Content to Our Website

- [flaticon](https://www.flaticon.com/)


## CSS Sizing

- `font-size` 可以是px，也可以是「百分比 or em」(動態)，若100%是16px，500%就是80px
- 16px = 100% = 1em
- 什麼時候決定用哪個？ 各有說詞 
- 但是要注意em跟%有繼承性質，如果`body`裡定義了2em，`h1`又定義5em，總共會有10em(但px只會以優先順序取，不會繼承疊加)
- css3有rem(不會繼承)


## CSS Float and Clear

- 本節想達到圖片可以在文字段落的兩側，靠`float`來達成(文繞圖)
- `line-height: 1.5` 行高
- 如果圖靠文字太近，可以加一點margin
- `float`不要拿來切版

```css
.chilli-img {
    width: 35%;
    border-radius: 2.5%;
    float: right;
    margin-left: 30px;
}
```

![](/img/6.png)

如果在`p`的另外設`clear`，會取消文繞圖

```css
.desc-code {
clear:left;
}

.desc-chilli {
    clear:right;
}

```

- [Flex](https://wcc723.github.io/css/2017/07/21/css-flex/)
- [前端挑戰](https://www.frontendmentor.io/)


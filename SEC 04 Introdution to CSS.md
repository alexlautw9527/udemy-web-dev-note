# Introduction to CSS

## Introduction to CSS

- 純html tag局限性很多又很難維護
- css讚

## Inline CSS

- 在進行定義的html tag裡面撰寫css
- `background-color`可以輸入hex
- 去color hunt找好看的顏色

```html
<body style="background-color: #C6D57E;">
    <h1>hi</h1>
</body>
```

## Internal CSS

- 碰到`<hr>`這種tag，若css定義在tag裡面要一個一個改很麻煩
- 裡用`<style></style>`統一定義css
- [HTML預設的css values](https://www.w3schools.com/cssref/css_default_values.asp) 大致一覽每一個html tag有哪些css
- 網頁上所有東西的本質就是一個一個"box"，參考[CSS Box Model](https://www.oxxostudio.tw/articles/202008/css-box-model.html)
- 若`<hr>`的`border-style`直接定義`none`，就沒有任何pixel。此時可以定義`heights` ，讓它成為一個實際的矩形，這時用`background-color`才有效果
- 可以定義成px or 百分比％
- `border-style`如果只設一個值，會直接四個邊都定義，但可以上下左右皆自由定義，也可以直接明確定義`border-top-style`
- 詳見  [MDN border-style](https://developer.mozilla.org/zh-CN/docs/Web/CSS/border-style)

``` html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>

<style>
    body {
       background-color: #D57E7E;   
    }

    hr {
      height: 20px;
      width: 30%;
      border-style: none;
      background-color: white;
    }    
</style>

<body>
    <h1>hi</h1>
    <hr>
    <h1>there</h1>
</body>
</html>
```


## External CSS

- 如果有許多html頁面要套用同一個css，internal css仍然不方便
- 此時把css定義另存成`.css`，就可以讓每個html套用
- 如果用/開頭，代表是絕對路徑

``` html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="css/styles.css">
    <title>Document</title>
</head>

<body>
    <h1>hi</h1>
    <hr>
    <h1>there</h1>
</body>
</html>
```

## How to Debug CSS Code

- 開啟chrome developer tools(F12)
- 到Console看錯誤訊息
- Element -> Styles 可以查看css的套用狀況   
- 優先順序: inline > internal > external，這樣才可以根據不同情況微調

## The Anatomy of CSS Syntax

- `selector {property:value;}`
- `h1 {color:red}`
- 多個property建議由字母開頭排序
- 想查有哪些propery，go MDN CSS ref

## CSS Selector

- 如果設定了`img`標籤的css，若無區分的話，css會作用在每一張圖片，很不方便
- 在`img`標籤自訂義class，就能在css Selector做出更精確的自定義


```html
<img class="bacon"></img>
<img class="broccoli"></img>
```

```css
/******tag selector******/

h1 {
  font-size:200px;   
}

/******class selector******/

.bacon {
  background-color:green;  
}

.broccoli {
  font-size:red;    
}
```

## Classes vs. Ids

- selector優先程度 id > class > tag
- 每一個id都要是unique，不能重複使用
- class是將風格相近的標籤組織在一起
- 一個html tag可以有兩個class，`<img class="broccoli radius"></img>`，就同時有roccoli和radius這兩個class，也會同時作用在這個html tag
- 但一個html tag只能套用一個id

```html
<h1 id="heading"></img>
```


```css
/******tag selector******/

h1 {
  font-size:200px;
  background-color:red;  
}

/******class selector******/

.bacon {
  background-color:green;  
}

.broccoli {
  font-size:red;    
}

/******id selector******/


#heading{
  background-color:blue;  
}
```

### pseudo class

- 每個element根據使用者不同動作，有不同狀態，例如游標是不是在圖片上
- pseudo class 「:」開頭，例如`:hover`
- 如下方css定義，如果游標在圖片上的時候，圖片背景就會變為金色


```css
/******tag selector******/
img:hover{
  background-color:gold;  
}
```

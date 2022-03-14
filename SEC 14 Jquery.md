## What is jQuery?

把繁雜的DOM變簡單了

![](/img/20.png)


## How to Incorporate jQuery into Websites

- Use CDN，用比較大眾的CDN好處是，通常已被使用者存入快取

```html
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.6.0/jquery.min.js"></script>
```

```js
$("h1").css("color", "red");
```


```js
//等網頁載入後再執行
$(document).ready(function(){
    $("h1").css("color", "red");
});
```

有可能網頁html還沒加載完成，index.js已開始執行，導致執行失敗，可以設定加載完成才執行

或是把script部分放在body後面也行


## How Minification Works to Reduce File Size

- minify.org

js or css 實際上線後，可以刪除不必要的空白字元減少程式碼檔案容量


## Selecting Elements with jQuery

```
$("cssSelector")

$("#header")

$("h1.my-class")
```

## Manipulating Styles with jQuery

```js
// 回傳css屬性
$("h1").css("color");

//改變css屬性
$("h1").css("color", "red");

```

不過根據三劍客各司其職的概念，在js裡直接設定css屬性不是很好的做法，建議是在css裡面先寫好class，利用jquery add class來改變屬性

```js
$("h1").addClass("my-class1 my-class2")
$("h1").removeClass("my-class1 my-class2")
$("h1").hasClass("my-class1") //回傳boolean
```

## Manipulating Text with jQuery

```js
$("h1").text("hi") //改變text
$("h1").html("<em>hey</em>") //改變inner html

```

## Manipulating Attributes with jQuery

```
$("img").attr("src")
$("a").attr("href", "https://www.google.com")
```

## Adding Event Listeners with jQuery

dom vs jquery

![](/img/21.png)

更統一的寫法: on + event

![](/img/23.png)

## Adding and Removing Elements with jQuery

```js
//添加元素
$("h1").before()
$("h1").after()
$("h1").prepend()
$("h1").append()

$("button").remove() //刪除button

```

![](/img/24.png)


## Website Animations with jQuery

```

$().hide()
$().show()

$().fadeOut()
$().fadeIn()

$().fadeToggle()

$().slideToggle()

$().animate({opacity:0.5}) //放數值型css

$().fadeIn().animate({opacity:0.5}) //串一起

```
## What is Bootstrap?

- 前端介面的套件，可重複利用
- 輕鬆讓網站有RWD頁面   
- 之前要用button generator貼上一堆css才能有好看的按鈕，bootstrap已提供許多Pre-styled element
- [codeply: 可以用框架的codepen](https://www.udemy.com/course/the-complete-web-development-bootcamp/learn/lecture/12287906#overview)

```html
<botton class="btn btn-primary"> hello </botton>
```
如此就有hover效果

- 可從boostrap原始程式碼研究
- 不只會套用，還要知道底層

## Installing Bootstrap

- boostrap的code是hosted CDN，可以提升載入速度
- 更有可能使用者的瀏覽器已經有快取

起手式模板

```html
<!doctype html>
<html lang="en">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">

    <!-- Bootstrap CSS -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3" crossorigin="anonymous">

    <title>Hello, world!</title>
  </head>
  <body>
    <h1>Hello, world!</h1>

    <!-- Optional JavaScript; choose one of the two! -->

    <!-- Option 1: Bootstrap Bundle with Popper -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-ka7Sk0Gln4gmtz2MlQnikT1wXgYsOg+OMhuP+IlRH9sENBO0LRn5q+8nbTov4+1p" crossorigin="anonymous"></script>

    <!-- Option 2: Separate Popper and Bootstrap JS -->
    <!--
    <script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.10.2/dist/umd/popper.min.js" integrity="sha384-7+zCNj/IqJ95wo16oMtfsKbZ9ccEh31eOz1HGyDuCQ6wgnyJNSYdrPa03rtR1zdB" crossorigin="anonymous"></script>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/js/bootstrap.min.js" integrity="sha384-QJHtvGhmr9XOIpI6YVutG+2QOK9T+ZnN4kzFN1RtK3zEFEIsxhlmWl5/YESvpZ13" crossorigin="anonymous"></script>
    -->
  </body>
</html>
```

## Web Design 101 - Wireframing

- low fidelity: 用鉛筆或黑白先設計原型
- mock-up: 很接近實際介面

- [awwwards: 各種很讚ㄉ網頁設計](https://www.awwwards.com/)
- [UI pattern](http://ui-patterns.com/patterns)
- [dribbble: 也很多好看的設計](https://dribbble.com/)
  - 還可以用顏色搜尋

- [sneakpeekit: 做wireframing的模板](https://sneakpeekit.com/)

## The Bootstrap Navigation Bar

- 只要下好class，就能正確套用模板，創造有模有樣的navbar
- `lg`vs`md`: [響應式斷點](https://bootstrap5.hexschool.com/docs/5.0/layout/breakpoints/)
- 在bootstrap 5，`ml-auto`改為`ms-auto`
- [start vs left](https://stackoverflow.com/questions/63948287/bootstrap-5-navbar-align-items-right)



```html
<nav class="navbar navbar-expand-md navbar-dark bg-dark">
    
    <a class="navbar-brand" hred="">Alex</a>
    
    <!--讓元素可以匯聚成一個選單按鈕, 在下面用div包起來-->
    <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
    </button>
    <!--
    data-target="#navbarSupportedContent"
    要對到div id
    -->
    <div class="collapse navbar-collapse" id="navbarSupportedContent"> 
    
    <ul class="navbar-nav ml-auto" >
      <li class="nav-item">
        <a class="nav-link" href="#">Home</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Features</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Pricing</a>
    </ul>
    </div>    
</nav>
```

- [官方docs](https://getbootstrap.com/docs/4.3/components/navbar/)

## Bootstrap Grid Layout System 

- 學習用Boostrap切版，並且自定義RWD
- `class="col-md-4"`:  在md尺寸以上佔據4/12，小於threshold就變成12/12

- `class="col-lg-2 col-md-4 col-sm-6 col-12"`: 
  - `col-`: RWD最小切點時，每個佔據12/12
  - `col-sm`: 在手機大小時，每個佔據6/12
  - `col-md`: 在平板大小時，每個佔據4/12
  - `col-lg`: 在桌機螢幕大小時，每個佔據2/12
  - 只有`col-`而無其他斷點時，就是無RWD通用

```html
  <div class="container">
  <div class="row">
    <div class="col" style="background-color:grey; border: 1px solid">
      等寬
    </div>
    <div class="col" style="background-color:grey; border: 1px solid">
      等寬
    </div>
    <div class="col" style="background-color:grey; border: 1px solid">
      等寬
    </div>
   </div>
    
  <div class="row">
    <div class="col" style="background-color:white; border: 1px solid">
      1 of 3
    </div>
    <div class="col-5" style="background-color:white; border: 1px solid">
     佔據5/12
    </div>
    <div class="col" style="background-color:white; border: 1px solid">
      3 of 3
    </div>
  </div>
  
  <div class="row">
    <div class="col-lg-2 col-md-4 col-sm-6 col-12" style="background-color:white; border: 1px solid">
        1
    </div>
    <div class="col-lg-2 col-md-4 col-sm-6 col-12" style="background-color:white; border: 1px solid">
        2
    </div>
    <div class="col-lg-2 col-md-4 col-sm-6 col-12" style="background-color:white; border: 1px solid">
        3
    </div>
    <div class="col col-12 col-sm-6 col-md-4 col-lg-2" style="background-color:white; border: 1px solid">
        4
    </div>
    <div class="col col-12 col-sm-6 col-md-4 col-lg-2" style="background-color:white; border: 1px solid">
        5
    </div>
    <div class="col col-12 col-sm-6 col-md-4 col-lg-2" style="background-color:white; border: 1px solid">
        6
    </div>
    
  </div>
  
  </div>
```

- [40行實作響應式的佈局系統 — 告訴你col-sm-12、col-md-6 是如何實現](https://realdennis.medium.com/40%E8%A1%8C%E5%AF%A6%E4%BD%9C%E9%9F%BF%E6%87%89%E5%BC%8F%E7%9A%84%E4%BD%88%E5%B1%80%E7%B3%BB%E7%B5%B1-%E5%91%8A%E8%A8%B4%E4%BD%A0col-sm-12-col-md-6-%E6%98%AF%E5%A6%82%E4%BD%95%E5%AF%A6%E7%8F%BE-4490a65b1a0)


## Getting Montserrat Black and other Font Weights

[Montserrat](https://fonts.google.com/specimen/Montserrat)

可選多個字重

```html
<link rel="preconnect" href="https://fonts.googleapis.com"> 
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin> 
<link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@100;400;900&display=swap" rel="stylesheet">
```

```css
h1 {  
  font-family: 'Montserrat, sans-serif';  
  font-size: 3rem;  
  line-height: 1.5;  
  font-weight: 900;
}
```

或是

```css
h1 {  
  font-family: 'Montserrat, sans-serif';  
}

body {  
  font-family: 'Montserrat-Black, sans-serif';  

}

```

## A Note About CSS Link Order

```css
<link rel="stylesheet" href="styles1.css">
<link rel="stylesheet" href="styles2.css">
```
若同一個屬性有重複設定，style2.css會覆寫（以排序後面為優先）

```css
<link href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/css/bootstrap.min.css" rel="stylesheet">
<link rel="stylesheet" href="css/styles.css">
```
先載入boostrap，再載入客製化css

## Bootstrap Containers 

boostrap的區塊容器。`containe-fluid`可以佔100% width

```html
<div class="container" style='background-color:gray'>
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus in dui a sem aliquam consequat. Maecenas sed feugiat enim, sed efficitur urna. Fusce sit amet diam dictum, feugiat elit non, maximus mauris. Vivamus placerat interdum quam, eu tincidunt mi lobortis vel.
</div>

<div class="container-fluid" style='background-color:green'>
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus in dui a sem aliquam consequat. Maecenas sed feugiat enim, sed efficitur urna. Fusce sit amet diam dictum, feugiat elit non, maximus mauris. Vivamus placerat interdum quam, eu tincidunt mi lobortis vel. 
</div>

```

![](/img/7.png)

另外可以在css裡面再客製化

```css
.container-fluid {
    padding: 3% 15%;
}
```

## Bootstrap Buttons & Font Awesome

### button

[button doc](https://getbootstrap.com/docs/4.0/components/buttons/)

#### Outline Buttons

``` html
<button type="button" class="btn btn-outline-primary">Primary</button>
```

#### Sizes

``` html
<button type="button" class="btn btn-primary btn-lg">Large button</button>
<button type="button" class="btn btn-primary btn-sm">Small button</button>

```

### icon

[fontawesome - 好看的icon](https://fontawesome.com/start)

先申請CDN，再放上`head`下面


```html
<script src="https://kit.fontawesome.com/5f335d9a7a.js" crossorigin="anonymous"></script>
```

再直接呼叫

https://fontawesome.com/v5.15/icons/apple?style=brands

```html
<i class="fab fa-apple"></i>
```

## Styling Our Website Challenges and Solutions

主要對風格進行優化

```css

/*元素間留白*/
.nav-item {
    padding: 0 18px;
}


.navbar {
    padding: 0 0 4.5rem;
}

.navbar-brand {
    font-family: 'Ubuntu', sans-serif;
    font-size: 2.5rem;
}
```

修正padding

![](/img/8.png)

```css
.navbar {
    padding: 0 0 4.5rem;
}
```

新增一個class加入到btn裡面改變padding

```html
<button type="button" class="btn btn-dark btn-lg dl-btn">
```

```css
.dl-btn{
    margin: 5% 3% 5% 0%;
}
```


## Solution to Bootstrap Challenge 1

### icon微調

```html
<i class="icon fas fa-check-circle fa-4x"></i>
```

`.fa-4x`可以讓icon變大，但其實改變`.fas`的`font-size`也可行。

不過盡量以增加custom class為主，直接動bootrap或awesome font的class會造成全局性異動，像這裡就直接加上`.icon`


```css
.icon {
    margin: 1rem;
    color: #ef8172;
}

.icon:hover {
    color: #ff4c58;
}

/*游標經過時變色*/
```

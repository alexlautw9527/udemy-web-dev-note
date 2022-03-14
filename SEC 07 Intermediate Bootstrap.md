## The Bootstrap Carousel Part 1

VSC multi-cusor
- 用點的:  option+Click
- 用方向鍵: option+cmd 方向鍵

## The Bootstrap Carousel Part 2

(in Bootstrap5)

### 自動輪播機制

```html
<div id="carouselExampleSlidesOnly" class="carousel slide" data-bs-ride="carousel">
  <div class="carousel-inner">
    <div class="carousel-item active">
      <img src="..." class="d-block w-100" alt="...">
    </div>
    <div class="carousel-item">
      <img src="..." class="d-block w-100" alt="...">
    </div>
    <div class="carousel-item">
      <img src="..." class="d-block w-100" alt="...">
    </div>
  </div>
</div>
```

```css
.carousel-item {
    height: 200px;
}
```

可以定義間隔時間、hover時暫定輪播等等

`data-bs-interval="5000"`: 5秒
`data-bs-ride＝"false"`: 不自動輪播
`data-bs-pause="hover"`: hover時暫停

`class="carousel slide"`: 會有動畫
`class="carousel"`: 沒有動畫

### 加入控制項

```html

<div id="carouselExampleControls" class="carousel slide" data-bs-ride="false">
  <div class="carousel-inner">
    <div class="carousel-item active" style="background-color:black">
      <h1>Hello1 </h1>
    </div>
    <div class="carousel-item" style="background-color:grey">
      <h1>Hello2 </h1>
    </div>
    <div class="carousel-item" style="background-color:aqua">
      <h1>Hello3 </h1>
    </div>
  </div>
  <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleControls" data-bs-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Previous</span>
  </button>
  <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleControls" data-bs-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Next</span>
  </button>
</div>
```

注意`id="carouselExampleControls"` vs `data-bs-target="#carouselExampleControls" `要相同

`class="visually-hidden`: 視覺上會被隱藏顯示，但是可以被輔助使用功能讀取到
`aria-hidden="true"`: 不會被輔助使用聚焦到，提升使用體儼


對整個`<section>`使用padding會擠壓到next bar的空間，所以需要把padding改為設定在`.carousel-item `裡

## Bootstrap Cards

[Pricing example](https://getbootstrap.com/docs/5.0/examples/pricing/)

[bootsnipp 許多bootstrap實現](https://bootsnipp.com/)

```html
<!-- 用網格系統實現，有響應式 ，但還不能達到cards等高 -->
<div class="row row-cols-1 row-cols-md-3 mb-3 text-center">
      <div class="col">
        <div class="card mb-4 rounded-3 shadow-sm">
          <div class="card-header py-3">
            <h4 class="my-0 fw-normal">Free</h4>
          </div>
          <div class="card-body">
            <h1 class="card-title pricing-card-title">$0<small class="text-muted fw-light">/mo</small></h1>
            <ul class="list-unstyled mt-3 mb-4">
              <li>10 users included</li>
              <li>2 GB of storage</li>
              <li>Email support</li>
              <li>Help center access</li>
            </ul>
            <button type="button" class="w-100 btn btn-lg btn-outline-primary">Sign up for free</button>
          </div>
        </div>
      </div>
      <div class="col">
        <div class="card mb-4 rounded-3 shadow-sm">
          <div class="card-header py-3">
            <h4 class="my-0 fw-normal">Pro</h4>
          </div>
          <div class="card-body">
            <h1 class="card-title pricing-card-title">$15<small class="text-muted fw-light">/mo</small></h1>
            <ul class="list-unstyled mt-3 mb-4">
              <li>20 users included</li>
              <li>10 GB of storage</li>
              <li>Priority email support</li>
              <li>Help center access</li>
            </ul>
            <button type="button" class="w-100 btn btn-lg btn-primary">Get started</button>
          </div>
        </div>
      </div>
      <div class="col">
        <div class="card mb-4 rounded-3 shadow-sm border-primary">
          <div class="card-header py-3 text-white bg-primary border-primary">
            <h4 class="my-0 fw-normal">Enterprise</h4>
          </div>
          <div class="card-body">
            <h1 class="card-title pricing-card-title">$29<small class="text-muted fw-light">/mo</small></h1>
            <ul class="list-unstyled mt-3 mb-4">
              <li>30 users included</li>
              <li>15 GB of storage</li>
              <li>Phone and email support</li>
              <li>Help center access</li>
            </ul>
            <button type="button" class="w-100 btn btn-lg btn-primary">Contact us</button>
          </div>
        </div>
      </div>
</div>
```

先從頭開始刻

```html
<div class="card text-center">
  <div class="card-header">
    Featured
  </div>
  <div class="card-body">
    <h5 class="card-title">Special title treatment</h5>
    <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
  <div class="card-footer text-muted">
    2 days ago
  </div>
</div>
```

ps: bootstrap5把`card-deck`拿掉了，要改成`card-group`，包在一起就可以做成等高，如下：
(不過每個cards會相連再一起)


```html
<div class="card-group">

        <div class="card text-center">
          <div class="card-header">
            <h3>Chihuahua</h3>
          </div>
          <div class="card-body">
            <h2>Free</h2>
            <p>5 Matches Per Day</p>
            <p>10 Messages Per Day</p>
            <p>Unlimited App Usage</p>
            <button type="button">Sign Up</button>
          </div>
        </div>


        <div class="card text-center">
          <div class="card-header">
            <h3>Labrador</h3>
          </div>
          <div class="card-body">
            <h2>$49 / mo</h2>
            <p>Unlimited Matches</p>
            <p>Unlimited Messages</p>
            <p>Unlimited App Usage</p>
            <button type="button">Sign Up</button>
          </div>

      </div>

        <div class="card text-center">
          <div class="card-header">
            <h3>Mastiff</h3>
          </div>
          <div class="card-body">
            <h2>$99 / mo</h2>
            <p>Pirority Listing</p>
            <p>Unlimited Matches</p>
            <p>Unlimited Messages</p>
            <p>Unlimited App Usage</p>
            <button type="button">Sign Up</button>
          </div>
        </div>

    </div>
    
```

最終解法: 回歸grid system，`<li>`多插入`<br>`來讓高度一致，並再加上三個RWD斷點
(加入h-100會在行動版大小壞掉)

```html
<div class="row mb-3 text-center">
      <div class="col col-md-6">
        <div class="card mb-4 rounded-3 shadow-sm">
          <div class="card-header py-3">
            <h4 class="my-0 fw-normal">Free</h4>
          </div>
          <div class="card-body">
            <h1 class="card-title pricing-card-title">$0<small class="text-muted fw-light">/mo</small></h1>
            <ul class="list-unstyled mt-3 mb-4">
              <li>10 users included</li>
              <li>2 GB of storage</li>
              <li>Email support</li>
              <li>Help center access</li>
              <li><br></li>
            </ul>
            <button type="button" class="w-100 btn btn-lg btn-outline-primary">Sign up for free</button>
          </div>
        </div>
      </div>
      <div class="col col-md-6">
        <div class="card mb-4 rounded-3 shadow-sm">
          <div class="card-header py-3">
            <h4 class="my-0 fw-normal">Pro</h4>
          </div>
          <div class="card-body">
            <h1 class="card-title pricing-card-title">$15<small class="text-muted fw-light">/mo</small></h1>
            <ul class="list-unstyled mt-3 mb-4">
              <li>20 users included</li>
              <li>10 GB of storage</li>
              <li>Priority email support</li>
              <li>Help center access</li>
              <li><br></li>
            </ul>
            <button type="button" class="w-100 btn btn-lg btn-primary">Get started</button>
          </div>
        </div>
      </div>
      <div class="col col-md-12">
        <div class="card mb-4 rounded-3 shadow-sm border-primary">
          <div class="card-header py-3 text-white bg-primary border-primary">
            <h4 class="my-0 fw-normal">Enterprise</h4>
          </div>
          <div class="card-body">
            <h1 class="card-title pricing-card-title">$29<small class="text-muted fw-light">/mo</small></h1>
            <ul class="list-unstyled mt-3 mb-4">
              <li>30 users included</li>
              <li>15 GB of storage</li>
              <li>Phone and email support</li>
              <li>Help center access</li>
              <li>Help center access</li>
            </ul>
            <button type="button" class="w-100 btn btn-lg btn-primary">Contact us</button>
          </div>
        </div>
      </div>
</div>
```

ps:bootstrap 5的按鈕class沒有`.btn-block`，可以改用`.w-100`

## The CSS Z-Index and Stacking Order

- 預設是按照程式碼的順序來決定stacking order（越後面的越上面），但可以藉由`z-index`來決定順序
- 但`position`若為`staic`時，不會作用

![](/img/10.png)

[複習position](https://zh-tw.learnlayout.com/position.html)


```css
.title-img {
    width: 60%;
    position: absolute;
}
```

圖片會變超大，好像是boostrap5的關係...把`width`改為`max-width`


Fouad
72 upvotes
10 months ago
The problem is that it's not sized relative to the div. I think it's because of Bootstrap 5. I use the same and encountered the issue as well. My best guess is that a new change in any of the classes in Bootstrap 5 is causing the issue. I found an easy solution. Simply add a custom class to the div in which the image sits and add position: relative; to the div. That worked for me.

Oğuz Kaan
28 upvotes
6 months ago
Though Fouad's solution is the case, it is not Bootstrap related, I think. The CSS documentation states that absolute positioning sets the element relative to the closest positioned ancestor, which in this case the div containing the image, and positioned means anything besides static, hence absolute or relative. If the ancestor is not positioned, image is absolute positioned related to next positioned ancestor, and that is body, result is a huge width of 60% of the whole body.

Fouad
117 upvotes
10 months ago
Guys, I identified the exact problem. In bootstrap 4, the 'col' classes have 'position: relative;' functions. So naturally, when Angela changed the width of the image to 60%, it was relative to the col div. In bootstrap 5, the col classes don't have position: relative;. So you have to add it manually to the col div by adding a custom class like I mentioned above. Otherwise when you assign 60%, it will size it relative to the whole body of the website.

更簡單的解法：設marging負值

```css
.title-img {

  margin: auto auto -12rem 50px;

  transform: rotate(25deg);

  width: 60%;   

}

#features {

  text-align: center;

  padding: 7% 15%;

  background-color: #fff;

  position: relative; 

}
```


設完css後如下圖
```css
.title-img {
    width: 20%;
    position: absolute;
}

#features{
    text-align:center;
    padding: 3% 9%;
    position: relative;
    z-index: 1;

}
```

![](/img/11.png)

所以`#feature`記得把背景變白色(可是如果頁面是手機大小時會很奇怪，還是設margin為負值出來結果比較正常)

後記：其實不用設z-index，依照flow chart，iphone照片也會在白背景下面


### Media Query Breakpoints

現在用手機瀏覽網頁的情境比桌機還多了，行動版網頁很重要。如果不是mobile-friendly，似乎會影響搜尋排名

瀏覽器的大小: view-port 

[mobile-friendly test](https://search.google.com/test/mobile-friendly)

法1: 做兩個版本的網頁行動版vs桌機版(like fb)
法2: RWD

這次要在css 引入media-query的概念，可以用以微調RWD網頁，如下(可以想成是一個if then)


`@media <type> <feature>`

```css
@media (min-width: 900x){
    //sth
}
```

```css

h1 {
    font-size: 30px;
}

@media (min-width: 900x) and (max-width: 1000x) {
    h1 {
        font-size: 30px;
    }
}
```

```css
.title-img {
    width: 60%;
    position: absolute;
    transform: rotate(25deg);
    left:30%;
}

@media (max-width: 991px) {
    #title{
        text-align: center;
    }
    .title-img  {
        position: static;
        transform: rotate(0);
        width: 60%;
    }
}
```

可以利用media query，在行動版大小的時候從`absolute`改為`static`，進行版面最佳化


## Bootstrap Challenge 2 Solution

easy.

可直接跳轉至那個id的section

```html
<div class="collapse navbar-collapse" id="navbarSupportedContent">
    <ul class="navbar-nav ms-auto">
    <li class="nav-item">
        <a class="nav-link" href="#footer">Contact</a>
    </li>
    <li class="nav-item">
        <a class="nav-link" href="#pricing">Pricing</a>
    </li>
    <li class="nav-item">
        <a class="nav-link" href="#cta">Download</a>
    </li>
    </ul>
</div>
```

## How to become a Better Programmer - Code Refactoring

可以發現目前的code很多重複之處，可以再更近一步重構

重構的性質之重要程度可由上至下
- readablity
- modularity
- efficiency
- length

不要一味追求簡短而喪失可讀性
code golf

## Put it into Practice - Refactor our Website Part 1

盡量不要將h1,h2設定很特定的屬性，例如顏色、字高（這些從設定特定class來設定）。
好處是比較好debug，知道目前的element是被哪一段css影響

```css
h1, h2, h3, h5, h6 {
    font-family: 'Montserrat', sans-serif;
    font-size:1.5rem;
    font-weight: 900;
}


.big-heading {
    font-family: 'Montserrat', sans-serif;
    font-size:3rem;
    font-weight: 900;
}

.testimonials-text {
    font-size: 2rems;
  }

.section-heading  {
    font-size: 2ems;
}

.feature-title{
    font-size: 1.5rems;
}

.cta-heading{
    font-size: 1.5rems;
}
```

 - 如果某些屬性一直重複被設定，例如`text-align: center`，乾脆放到body一次設定，特定文字再設定`text-align: left`
 - 若有些padding設定一直重複被利用到，這時候就是container派上用場的時候了


```css

.container-fluid {
    padding: 7% 15%;
}

#title .container-fluid {
    padding: 3% 15% 7%;
}
```

`#title` section 裡面的.container-fluid才會套用`padding: 3% 15% 7%`這個屬性


## Advanced CSS - Combining Selectors

### multiple selector

`selector1, selector2{ }`

```css
h1, h2, h3 {
  color: red;
}
```

### Hierarchical selector

`selector1 selector2{ }`
（空白很重要） 通常使用class or id
有階層關係才會作用

```css
div h1 {color: red;}
/*這樣所有div裡的h1都會變紅色*/


.container-fluid h1 {color: red;}
/*特定class裡的h1變紅色*/

```

### Combined selector

`selector1selctor2 { }`
（沒有空白！）
同時出現這兩個selector才會作用

```css
h1#tittle {color:red}
/* 同時是h1也是#title 才會變紅色*/
```

## Refactoring our Website Part 2

因為各個section是白色紅色交替，創建一個class來決定背景顏色是合理的決定，而不用對每一個section id各別設定

## Advanced CSS - Selector Priority

優先性: 
html tag style > id css > class css > html tag css  

- 謹慎使用id，不要當成class在用（建議section才用id，或真的必要時）
- 避免一個element使用多個custom class，除非必要
- 別用inline style

 


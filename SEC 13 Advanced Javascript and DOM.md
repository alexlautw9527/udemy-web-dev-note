## Adding Event Listeners to a Button


Eventlistener: 可以設定點擊了之後，會執行函數
```js
document.querySelector("button").addEventListener("click", function(){
    alert('hi');
});

//匿名函數
```

把所有`button`加入Eventlistener

```js
btnArray = document.querySelectorAll("button")

for(let i=0; i<btnArray.length; i++){
    btnArray[i].addEventListener("click", function(){
        alert('hi');
    });
}
```

## Higher Order Functions and Passing Functions as Arguments
Higher Order Functions: 接受其他function作為參數傳入的function

```js
document.querySelector("button").addEventListener("click", function(){
    alert('hi');
});
```

其實就是把function作為參數

note: Chrome dev mode: console輸入debugger

```js
function add(num1, num2) {
return num1 + num2;
}
 
function subtract(num1, num2) {
return num1 - num2;
}
 
function multiply(num1, num2) {
return num1 * num2;
}
 
function divide(num1, num2) {
return num1 / num2;
}
 
function calculator(num1, num2, operator) {
return operator(num1, num2);
}
```

## How to Play Sounds on a Website

```js
var audio = new Audio('audio_file.mp3');
audio.play();
```

this: this的指向的是目前呼叫函式或方法的擁有者(owner)物件

```js
btnArray = document.querySelectorAll(".drum");

btnArray[0].addEventListener("click", function(){
    console.log(this)
});
```
此時this就會是`btnArray[0]`所參照的物件，這樣做可以是EventListener去改變目前物件的style


## A Deeper Understanding of Javascript Objects

object有點像python的dict

![](/img/13.png)

建構object的function constructor
![](/img/14.png)

![](/img/15.png)

當我們使用 new 這個關鍵字時，實際上會先有一個空的物件被建立。

接著函式會被執行（invoke）。我們知道當函式執行的時候，在 execution context 中會有 this 被建立，而當我們使用 new 的時候，函式裡面的 this 會被指定成剛剛所建立的那個空物件。

所以當執行 BellyBoy 這個 function，執行到 this.firstName，因為 this 現在指稱的是那個空物件，所以實際上是在幫這個空物件賦予屬性名稱和屬性值。

這裡有一個地方我們需要非常留意，如果你在程式撰寫的過程當中，忘記加上 new 這個關鍵字的話

如此，因為 JavaScript 不知道你是要執行這個程式，還是要根據這個 function 去建立object，因次最後回傳 undefined 的結果


## How to Use Switch Statements in Javascript

```js
btnArray = document.querySelectorAll(".drum");

for(let i=0; i<btnArray.length; i++){

    btnArray[i].addEventListener("click", function(){
        let btnInnerHTML = this.innerHTML;

        switch (btnInnerHTML){
            case "w":
                let crash = new Audio('sounds/crash.mp3');
                crash.play();
                break;
            case "a":
                let kick = new Audio('sounds/kick-bass.mp3');
                kick.play();
                break;
            case "s":
                let snare = new Audio('sounds/snare.mp3');
                snare.play();
                break;
            case "d":
                let tom1 = new Audio('sounds/tom-1.mp3');
                tom1.play();
                break;
            case "j":
                let tom2 = new Audio('sounds/tom-2.mp3');
                tom2.play();
                break;
            case "k":
                let tom3 = new Audio('sounds/tom-3.mp3');
                tom3.play();
                break;
            case "l":
                let tom4= new Audio('sounds/tom-4.mp3');
                tom4.play();
                break;
            
            default: console.log('hi')
        }
    });
};

```

## Objects, their Methods and the Dot Notation

![](/img/16.png)
    
## Using Keyboard Event Listeners to Check for Key Presses

確認按下按鍵會回傳什麼

```js
window.addEventListener('keydown', function(e){
  console.log(e)
}, false);
```

![](/img/17.png)


```js
btnArray = document.querySelectorAll(".drum");

for(let i=0; i<btnArray.length; i++){

    btnArray[i].addEventListener("keydown", function(e){
        let keyPressed = e.key;

        switch (keyPressed){
            case "w":
                let crash = new Audio('sounds/crash.mp3');
                crash.play();
                break;
            case "a":
                let kick = new Audio('sounds/kick-bass.mp3');
                kick.play();
                break;
            case "s":
                let snare = new Audio('sounds/snare.mp3');
                snare.play();
                break;
            case "d":
                let tom1 = new Audio('sounds/tom-1.mp3');
                tom1.play();
                break;
            case "j":
                let tom2 = new Audio('sounds/tom-2.mp3');
                tom2.play();
                break;
            case "k":
                let tom3 = new Audio('sounds/tom-3.mp3');
                tom3.play();
                break;
            case "l":
                let tom4= new Audio('sounds/tom-4.mp3');
                tom4.play();
                break;
            
            default: console.log('hi')
        }
    });
};
```

## Understanding Callbacks and How to Respond to Events

- High Order Function: 接受function作為參數傳遞的function

![](/img/18.png)

![](/img/19.png)

## Adding Animation to Websites

- 透過addclass實現動畫
- 透過setTimeOut移除class來回復原狀

```js
function buttonAnimation(currentKey) {

  var activeButton = document.querySelector("." + currentKey);

  activeButton.classList.add("pressed");

  setTimeout(function() {
    activeButton.classList.remove("pressed");
  }, 100);

}

```

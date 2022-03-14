## Random Number Generation in Javascript: Building a Love Calculator

```
Math.random()
```
產生0 = 0.999999999之間的數，[0,1)


```javascript

//0~100的隨機亂數
let randomPercent = Math.floor(Math.random()*100)+1
```

## Control Statements: Using If-Else Conditionals & Logic

```
if(track==='clear'){
    goStraight();
} else {
    turnRight();
}

```
## Comparators and Equality

```javascript
== //自動轉型別
===
!= //自動轉型別
!==
>
<
>
>=
<=  
```

## Combining Comparators

```javascript
&& //and
|| //or
! //not
```

## Coding Exercise 5: BMI Calculator Advanced (IF/ELSE)

```javascript
function bmiCalculator (weight, height) {
    let bmi = weight/(height*height)
    let word = ""
    if(bmi>24.9){
      word = "Your BMI is " +bmi+", so you are overweight."
    } else if(bmi<18.5) {
      word = "Your BMI is " +bmi+", so you are underweight."
    } else {
      word = "Your BMI is " +bmi+", so you have a normal weight."
    }

    return word;
}

bmiCalculator(100,2)
```

## Coding Exercise 6: Leap Year Challenge Exercise

閏年判斷

```javascript

function isLeap(year){
  if((year%4===0) &amp;&amp; (year%100!==0)){
    return 'Leap year.';
  } else if(year%400===0){
    return 'Leap year.';
  } else{
    return 'Not leap year.';
  }
}
```


## Collections: Working with Javascript Arrays

```
var arr = ['Hey', 'Hi', 'Hello'];
arr.length; //3
arr[0]; //'Hey'
arr.includes('Hi');// true
```

## Adding Elements and Intermediate Array Techniques

- Coding horror

``` javascript
let arr = []
let count = 1
function fizzBuzz(){
  if(count%15 ===0){
    arr.push('fizzBuzz');
  } else if(count%3 ===0){
    arr.push('fizz');
  } else if(count%5 ===0){
    arr.push('Buzz');
  } else{
  arr.push(count);
  }
  count++;
}

fizzBuzz();
fizzBuzz();
fizzBuzz();
fizzBuzz();
fizzBuzz();
fizzBuzz();
fizzBuzz();
fizzBuzz();
fizzBuzz();
fizzBuzz();
fizzBuzz();
fizzBuzz();
fizzBuzz();
fizzBuzz();
fizzBuzz();
fizzBuzz();

console.log(arr);


/*
[
  1,          2,
  'fizz',     4,
  'Buzz',     'fizz',
  7,          8,
  'fizz',     'Buzz',
  11,         'fizz',
  13,         14,
  'fizzBuzz', 16
]
*/
```

## Who's Buying Lunch Solution

```
let arr = ["Angela", "Ben", "Jenny", "Michael", "Chloe"]

function whosPaying(names){
  let who = Math.floor(Math.random()*names.length);
  return names[who] + " is going to buy lunch today!";
}

whosPaying(arr);
```

## Control Statements: While Loops

- freecodecamp

## Control Statements: For Loops

- freecodecamp

![](/img/12.png)

何時要用while or for?
- while: 檢查狀態
- for: 迭代

## Introducing the Fibonacci Code Challenge

```javascript
function fibonacciGen(n){
  if (n==1){
    return [0];
  } 
  else if(n==2){
    return [0,1];
  } 
  else {
    let arr = [0,1]
    for (var i=2; i<n; i++){
      lastIndex = arr.length-1
      last2Index = arr.length-2
      newNumber = arr[lastIndex] + arr[last2Index]
      arr.push(newNumber);   
    } 
    return arr;
  }
}

fibonacciGen(10)
```


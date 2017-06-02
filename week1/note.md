# Week 1
## Day 1
- Copy a fire from other directory to the current one
`cp ../test .`

- Show variable in the environment
`env`

- ### Java script

- #### Java script comparison
- [java script comparison table](https://dorey.github.io/JavaScript-Equality-Table)
* ` === ` exact equal
* ` == ` convert to the type then compare

- #### values
- number
- boolean
- string

- #### demo
```javascript
console.log('hello');
if (5 > 4) {
  console.log("math is easy");
}

var wdi12 = true;// global variable

// scope

if (wdi12) {
  console.log("wdi12 rocks!");
}

// truthy and falsey

// varlues that are falsey - false, empty string, 0, undefined, null, NaN
var name = "danny";
if (name) {
  console.log("hello " + name);
}
// return true


var points = 0;
if (points) {
  console.log("you have " + points);
}
// return false

var firstname;
if (firstname) {
  console.log("your name is " + firstname);
}
// return false

var uuu = 5==5 ? 5: 8
console.log(uuu);
```
- #### Git hub

* clone the git `git clone <url>`
* put file to staging area `git add -A`
* commit to git `git commit -m <"message">`
* push it up to git hub `git push origin master`
* ~~push git to your own repo `git push -u origin master`~~
* if use `git init` for the first time wee need `git remote add origin <url>`

```
$ git config user.name
$ git config user.email
$ git config --global color.ui auto
$ git config --global user.name
$ git config --global user.email
```
***
## Day 2

* #### convert a string into number

```javascript
Number("42")
parseInt("42")
parseFloat("42")
```

* #### to find dividble of 3/5/3 and 5
```javascript
for (var num = 1; num <= 100; num++) {
  var returnString = ""
  if (num % 3 == 0) {
    returnString += "Cake"
  }
  if (num % 5 == 0) {
    returnString += "Pudding"
  }
  if (returnString === "") {
    console.log(num);
  } else {
    console.log(returnString);
  }
}
```

* #### guessing game

```javascript
var secretNumber = 42
var guess = prompt('Enter a number between 1 to 100');

while (guess != secretNumber) {
  if (guess > secretNumber) {
    guess = prompt("Please guess a lower number");
  } else if (guess < secretNumber){
    guess = prompt("Please guess a higher number");
  } else {
    guess = prompt("Please enter a number")
  }
}
console.log("You got it right!");
```

* #### pyramid
```javascript
var line = 5
var max = line * 2 - 1
for (var num = 1; num <= max; num ++) {

  if (num % 2 != 0){
    var returnString = ""

    var space = (max - num) / 2
    var spaceCount = 0

    while (spaceCount != space) {
      if (space < 0) {
        break;
      }
      returnString += " ";
      spaceCount ++;
    }

    var symbleCount = 0

    while (symbleCount != num) {
      returnString += "$";
      symbleCount ++;
    }
    console.log(returnString);
  }
}
```
output:
```
     $
    $$$
   $$$$$
  $$$$$$$
 $$$$$$$$$
```
## day3
- array functions
- functions

## day4
- typeof : check the type of a variable

```javascript
// function expression
var doubleMe = function(number) {
  return number + number
}

// function declaration
// function doubleMe(number) {
//   return number + number
// }

console.log(doubleMe(5));

// passing multiple parameter will ignore the first one
console.log(doubleMe(10, 2))

var calmYourself = function(stuff) {
  return stuff.toLowerCase().replace("!", "")
}

console.log(calmYourself("NOOOOOOOOO!"));

var launchMissile = function() {
  var numberOfMissile = 3;

  console.log(numberOfMissiles + " missiles launched");
  console.log("missed all targets");
}

```

- exercise
```javascript
// 1. Write a function named calculateAge that:
// - takes 2 arguments: birth year, current year.
// - calculates the 2 possible ages based on those years.
// outputs the result to the screen like so: "You are either 100 or 101"
// - Call the function three times with different sets of values.

// your code here

var calculateAge = function(birthYear, currentYear) {

  if (currentYear > birthYear) {
    return "You are either " + (currentYear - birthYear - 1) + " or " + (currentYear - birthYear) + " years old"
  } else if (currentYear === birthYear) {
    return "You were born this year"
  } else {
    return "You haven't born yet"
  }



}
console.log(calculateAge(1993, 2017));
console.log(calculateAge(2017, 2017));
console.log(calculateAge(2018, 2017));

//  2. Write a function `lengths` that accepts a single parameter as an argument, namely
// an array of strings. The function should return an array of numbers where each
// number is the length of the corresponding string.

// your code here
var arr = ["A","ab","abc","sdhaskjdkash"]

var lengths = function(stringArray) {
  var returnArray = []
  for (var index = 0; index < stringArray.length; index ++) {
    returnArray.push(stringArray[index].split('').length)
  }
  return returnArray
}
console.log(lengths(arr));

// 3. Write a Javascript function called `transmogrifier`
// This function should accept three arguments, which you can assume will be numbers.
// Your function should return the "transmogrified" result
//
// The transmogrified result of three numbers is the product of the first two numbers,
// raised to the power of the third number.

// your code here
var transmogrifier = function(first, second, third) {
  return Math.pow((first * second), third)
}

console.log(transmogrifier(2,2,3));

// 4. Write a function `wordReverse` that accepts a single argument, a string. The
// method should return a string with the order of the words reversed. Don't worry
// about punctuation.

// your code here
var wordReverse = function(inputString) {
    return inputString.split(" ").reverse().join(" ");
}
console.log(wordReverse("apple pen"));
```


## day5
#### how to solve a problem
- Visulise
  - Flow diagram
- Algorithm
- Implementation

#### using js to change background color
```javascript
// find the button
var btn = document.getElementsByTagName('button')[0]

// find the body (entire page)
var body = document.body;

// listen to the click event

// add event listener is a function that takes 2 arguments. first one is the event,
// second argemnet is a function
var colorChanged = false
var changeColour = function() {
  colorChanged = !colorChanged
  document.body.style.backgroundColor = colorChanged ? randomRgbColor() : "white"
}


body.addEventListener("click", changeColour)


function randomRgbColor() {
  var r = Math.floor(Math.random() * 256)
  var g = Math.floor(Math.random() * 256)
  var b = Math.floor(Math.random() * 256)
  return "rgb(" + r + "," + g + "," + b +  ")"
}

```

#### forloop optional
```javascript
var i = 0;
for (;i < 3;) {
  console.log(i);
  i++
}
```

- any variable that is not defined inside a function, it is global

- object
```javascript
var fruit = {}
fruit.apple = 200
fruit["mango"] = 300
```

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

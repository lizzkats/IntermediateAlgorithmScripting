# IntermediateAlgorithmScripting
unhealthy-weaver

## Description

Complete the intermediate algorithm scripting section here:
https://www.freecodecamp.com/map


## Specifications

- [x] Completed Intermediate Algorithm Scripting 

### Required

_Do not remove these specs - they are required for all goals_.

- [x] The artifact produced is properly licensed, preferably with the [MIT license][mit-license].

## Stretch Goal

- [x] Supplement with TeamTreehouse Tutorials 
- [x] Complete 1-2 Intermediate Front End Projects 

## Quality Rubric

_What are some appropriate quality objectives for this goal? These are statements about the internal characteristics of the product that demonstrate fine design and craftspersonship, not its external features._

- Quality rubric one: Code is readable

## Sum All Numbers 
Sum all numbers in a range.
```javascript
function sumAll(arr) {
  
  var lower = 0;
  var higher = 0;
  if (arr[0] > arr[1]) {
    lower = arr[1];
    higher = arr[0];
  } else {
    lower = arr[0];
    higher = arr[1];
  }
  var sum = 0;
  for (var i= lower; i <= higher; i++){
    sum += i;
  }
  return sum;
}

sumAll([1, 4]);
```
## Diff Two Arrays
1- Compare two arrays and return a new array with any items only found in one of the two given arrays, but not both. In other words, return the symmetric difference of the two arrays.

```javascript

function diffArray(arr1, arr2) {
  var newArr = [];
  
for (var i=0; i < arr1.length; i++){
  if (arr2.indexOf(arr1[i]) === -1){
    newArr.push(arr1[i]);
  }
}
  // Take two arrays and compare them to see if items match between arrays. 
 // loop through arrays to check if arr[1] is indexof arr[0]. 
  // 
  
  for (var j=0; j < arr2.length; j++){
    if (arr1.indexOf(arr2[j]) === -1){
      newArr.push(arr2[j]);
    }
  }
  return newArr;
}

diffArray([1, 2, 3, 5], [1, 2, 3, 4, 5]);
```
## Roman Numeral Converter
2- Convert the given number into a roman numeral. 

```javascript


function convertToRoman(num) {
  var decimalValue = [ 1000, 900, 500, 400, 100, 90, 50, 40, 10, 9, 5, 4, 1 ];
  var romanNumeral = [ 'M', 'CM', 'D', 'CD', 'C', 'XC', 'L', 'XL', 'X', 'IX', 'V', 'IV', 'I' ];
  
  var converttoRoman = "";
  //loop while index fits into num 
  for (var i=0; i < decimalValue.length; i++) {
    while (decimalValue[i] <= num){
      converttoRoman += romanNumeral[i];
      num -= decimalValue[i];
    }
  }
 return converttoRoman;
}

convertToRoman(36);
```

## Wherefore art thou
Make a function that looks through an array of objects (first argument) and returns an array of all objects that have matching property and value pairs (second argument). Each property and value pair of the source object has to be present in the object from the collection if it is to be included in the returned array.
```javascript
function whatIsInAName(collection, source) {
  // What's in a name?
  var arr = [];
  // Only change code below this line
    var keysSource = Object.keys(source);
  //loop through the array to match source to collection
  //if the keys dont match the source return false
  return collection.filter(function (obj) {
    for(var i = 0; i < keysSource.length; i++) {
      if(!obj.hasOwnProperty(keysSource[i]) || obj[keysSource[i]] !== source[keysSource[i]]) {
        return false;
      }
    }
    return true;
  });
}
```
## Search and Replace
Perform a search and replace on the sentence using the arguments provided and return the new sentence.

```javascript

function myReplace(str, before, after) {
  
    // Find place where before is on string
  var index = str.indexOf(before);
  // Check to see if the first letter is uppercase or not
  if (str[index] === str[index].toUpperCase()) {
    // Change the after word to be capitalized before we use it.
    after = after.charAt(0).toUpperCase() + after.slice(1);
  }
  // Now replace the original str with the edited one.
  str = str.replace(before, after);

  return str;
}
```
## Pig Latin
 Translate the provided string into pig latin.

```javascript


function translatePigLatin(str) {
  var pigLatin ="";
  var regex = /[aeiou]/gi;
//check if first character is a vowel
  
  if (str[0].match(regex)) {
    pigLatin = str + 'way';
  } else {
    //find how many consonants before first vowel
    
    var vowelIndex = str.indexOf(str.match(regex)[0]);
    
    pigLatin = str.substr(vowelIndex) + str.substr(0, vowelIndex) + 'ay';
  }
  
  return pigLatin;
}

translatePigLatin("consonant");
```

## DNA Pairing 
The DNA strand is missing the pairing element. Take each character, get its pair, and return the results as a 2d array.
```javascript
var DNA_PAIRS = {
  'A': 'T',
  'C': 'G',
  'T': 'A',
  'G': 'C'
};


var makePair = function makePair(base) {
  var pair = DNA_PAIRS[base];
  return [base, pair];
};

console.log(makePair('A'));

function pairElement(dnaString) {
  var bases = dnaString.split('');
  var strand = bases.map(function (base) {
    return makePair(base);
  });

  return strand;
}
```

## Missing Letters

Find the missing letter in the passed letter range and return it.

```javascript

function fearNotLetter(str) {
  

for(var i=0; i<str.length-1; i++) {
  if(str.charCodeAt(i+1)-str.charCodeAt(i) !== 1) {
  str = String.fromCharCode(str.charCodeAt(i) + 1);
  }
    }
  if (str.length === 1) {
    return str;
  } 
  else 
  {
  return undefined;}
}


fearNotLetter("abce");
```
## Boo Who 

Check if a value is classified as a boolean primitive. Return true or false.

```javascript 

function booWho(bool) {
  // What is the new fad diet for ghost developers? The Boolean.
 
  return typeof bool === 'boolean';
}

booWho(null);
```

## Sorted Union
Write a function that takes two or more arrays and returns a new array of unique values in the order of the original provided arrays.
 ```javascript
 
  function uniteUnique(arr1, arr2, arr3) {
var newArr;
var args = Array.prototype.slice.call(arguments);
newArr = args.reduce(function(arrA,arrB) {
return arrA.concat(arrB.filter(function(i) {
return arrA.indexOf(i) === -1;
}));
});
return newArr;
}

uniteUnique([1, 3, 2], [5, 2, 1, 4], [2, 1]);
```

## Convert HTML Entities
Convert the characters &, <, >, " (double quote), and ' (apostrophe), in a string to their corresponding HTML entities.

```javascript
function convertHTML(str) {
  // Use Object Lookup to declare as many HTML entities as needed.
  htmlEntities={
    '&':'&amp;',
    '<':'&lt;',
    '>':'&gt;',
    '\"':'&quot;',
    '\'':"&apos;"
  };
  //Use map function to return a filtered str with all entities changed automatically.
  return str.split('').map(function(entity){
    return htmlEntities[entity] || entity;
  }).join('');
}

// test here
convertHTML("Dolce & Gabbana");
```

## Spinal Tap Case
Convert a string to spinal case. Spinal case is all-lowercase-words-joined-by-dashes.
```javascript
var spacesBeforeCapitals = function spacesBeforeCapitals(str) {
  return str.replace(/(.)([A-Z])/g, "$1 $2");
};
var hyphensInsteadOfSpacesOrUnderscores = function hyphensInsteadOfSpacesOrUnderscores(str) {
  return str.replace(/[ _]+/g, '-');
};

function spinalCase(str) {
  str = spacesBeforeCapitals(str);
  str = str.toLowerCase();
  str = hyphensInsteadOfSpacesOrUnderscores(str);

  return str;
}
```

## Sum All Odd Fibonacci Number 

Given a positive integer num, return the sum of all odd Fibonacci numbers that are less than or equal to num.

```javascript

function sumFibs(num) {

var previousNumber = 0;
var currentNumber = 1;
var result = 0;
while (currentNumber <= num) {
if (currentNumber % 2 !== 0) {
result += currentNumber;
}
var addedNumber = currentNumber + previousNumber;
previousNumber = currentNumber;
currentNumber = addedNumber;
}

return result;
}

sumFibs(4);
```
## Sum All Primes

Sum all the prime numbers up to and including the provided number.

```javascript

function sumPrimes(num) {
  // function to check if the number presented is prime
  function isPrime(number){
      for (i = 2; i <= number; i++){
          if(number % i === 0 && number!= i){
          // return true if it is divisable by any number that is not itself. 
             return false;
          }
       }
       // if it passes the for loops conditions it is a prime
      return true;
  }
  // 1 is not a prime, so return nothing, also stops the recusrive calls.
  if (num === 1){
    return 0;
  }
  // Check if your number is not prime
  if(isPrime(num) === false){
  // for non primes check the next number down from your maximum number, do not add anything to your answer
    return sumPrimes(num - 1);
  }
  
  // Check if your number is prime
  if(isPrime(num) === true){
  // for primes add that number to the next number in the sequence through a recursive call to our sumPrimes function.
    return num + sumPrimes(num - 1);
  }
}

```

## Smallest Common Multiple

Find the smallest common multiple of the provided parameters that can be evenly divided by both, as well as by all sequential numbers in the range between these parameters.

```javascript

function smallestCommons(arr) {
// Sort array from greater to lowest
arr.sort(function(a, b) {
return b - a;
});

// Create new array and add all values from greater to smaller from the original array.
var newArr = [];
for (var i = arr[0]; i >= arr[1]; i--) {
newArr.push(i);
}

// Variables needed declared outside the loops.
var quote = 0;
var loop = 1;
var j;

// run code while n is not the same as the array length.
do {
quote = newArr[0] * loop * newArr[1];
for (j = 2; j < newArr.length; j++) {
if (quote % newArr[j] !== 0) {
break;
}
}

loop++;
} while (j !== newArr.length)

return quote;
}

smallestCommons([1, 13]);

```

## Finders Keepers 

Create a function that looks through an array (first argument) and returns the first element in the array that passes a truth test (second argument).

```javascript

function findElement(arr, func) {
   filterArr = arr.filter(func); //filter array with the function provided

  return filterArr[0]; //return the first element that returns true, or undefined if no elements return true
}


findElement([1, 2, 3, 4], function(num){ return num % 2 === 0; });
```

## Drop It 
Drop the elements of an array (first argument), starting from the front, until the predicate (second argument) returns true.
```javascript


function dropElements(arr, func) {
  
  var times = arr.length;
  for (var i=0; i<times; i++){
    if(func(arr[0])){
    } else {
      arr.shift(); 
    }
  }
  // Drop them elements.
  return arr;
}

dropElements([1, 2, 3], function(n) {return n < 3; });

```

## Steamroller

Flatten a nested array. You must account for varying levels of nesting.

```javascript

function steamrollArray(arr) {
  // I'm a steamroller, baby
  return arr.reduce(function (flat, toFlatten) {
  return flat.concat(Array.isArray(toFlatten) ? steamrollArray(toFlatten) : toFlatten);
  }, []);
  
}

steamrollArray([1, [2], [3, [[4]]]]);
```
## Binary Agents
Return an English translated sentence of the passed binary string.

```javascript
function binaryAgent(str) {
var binaryString = str.split(' ');
var unitedString = [];

for(i = 0; i < binaryString.length; i++) {
unitedString.push(String.fromCharCode(parseInt(binaryString[i], 2)));
}
return unitedString.join('');
}

binaryAgent("01000001 01110010 01100101 01101110 00100111 01110100 00100000 01100010 01101111 01101110 01100110 01101001 01110010 01100101 01110011 00100000 01100110 01110101 01101110 00100001 00111111");
```
## Everything be true 

Check if the predicate (second argument) is truthy on all elements of a collection (first argument).

```javascript
function truthCheck(collection, pre) {
  // Is everyone being true?
  var arr = [];
for (var i = 0; i < collection.length; i++) {
  if (collection[i][pre]) {
    arr.push('true');
  }
}
  if (collection.length === arr.length) {
    return true;
  }
  else {
    return false;
 }
 }

truthCheck([{"user": "Tinky-Winky", "sex": "male"}, {"user": "Dipsy", "sex": "male"}, {"user": "Laa-Laa", "sex": "female"}, {"user": "Po", "sex": "female"}], "sex");

```

## Arguments Optional

Create a function that sums two arguments together. If only one argument is provided, then return a function that expects one argument and returns the sum.

```javascript
function addTogether() {
  // Function to check if a number is actually a number
  // and return undefined otherwise.
  var checkNum = function(num) {
    if (typeof num !== 'number') {
      return undefined;
    } else
      return num;
  };

  // Check if we have two parameters, check if they are numbers
  // handle the case where one is not
  // returns the addition.
  if (arguments.length > 1) {
    var a = checkNum(arguments[0]);
    var b = checkNum(arguments[1]);
    if (a === undefined || b === undefined) {
      return undefined;
    } else {
      return a + b;
    }
  } else {
    // If only one parameter was found, returns a new function that expects two
    // Store first argument before entering the new function scope
    var c = arguments[0];

    // Check the number again, must be outside the function to about returning an object
    // instead of undefined.
    if (checkNum(c)) {
      // Return function that expect a second argument.
      return function(arg2) {
        // Check for non-numbers
        if (c === undefined || checkNum(arg2) === undefined) {
          return undefined;
        } else {
          // if numbers then add them.
          return c + arg2;
        }
      };
    }
  }
}

// test here
addTogether(2,3);

```


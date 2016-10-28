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

## Solution 0- sumAll
0- Sum all numbers in a range.
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



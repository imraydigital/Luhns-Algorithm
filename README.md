# Luhns Algorithm
The aim of this project is to develop a credit card validation program using vanilla JS to recreate Luhn's algorithm.
### Project structure

1. Declaration of variables

    This includes an array of valid credit card numbers, invalid credit card numbers, a mixed array of mystery valid and invalid card numbers and a batch  array bundling the aforementioned arrays into one for the purposes of testing program functionality.
    
2. Declaration of **validateCred()** function

    The purpose of the function is to evaluate a passed in `array` of digits to compare validity based on Luhn's algorithm. The passed in array is first stored in a temporary array  `let tempArray = array` in order to avoid manipulation of the original array. Next, the `const droppedNum = array[array.length - 1]` variable stores the final digit of the array, which is then removed from the end of the array using `tempArray.pop()` in order to comply with Luhn's algorithm functionality which begins from the digit placed second from the right.

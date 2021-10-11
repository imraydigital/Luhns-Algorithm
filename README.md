# Luhn's Algorithm
The aim of this project is to develop a credit card validation program using vanilla JS to recreate Luhn's algorithm.
### Project structure

1. Declaration of variables

    This includes an array of valid credit card numbers, invalid credit card numbers, a mixed array of mystery valid and invalid card numbers and a batch  array bundling the aforementioned arrays into one for the purposes of testing program functionality.
    
2. Declaration of **validateCred()** function

    The purpose of the function is to evaluate a passed in `array` of digits to compare validity based on Luhn's algorithm. The passed in array is first stored in a temporary array  `let tempArray = array` in order to avoid manipulation of the original array. Next, the `const droppedNum = array[array.length - 1]` variable stores the final digit of the array, which is then removed from the end of the array using `tempArray.pop()` in order to comply with Luhn's algorithm functionality which begins from the digit placed second from the right.

`tempArray` is then reversed `  reversedArray = tempArray.reverse();` and a for loop is executed to loop through all digits, using the modulus operator `%` to check index position. If a digit satisifies this condition it is then multipeld by two, with all two digit numbers being converted into a single digit number through addition of each indiviudal digit (for example 12 would equate to 3) - this is then added to the `sum` variable.

```
// Declare sum of digits variable
  let sum = 0;
  // Loop through numbers
    for (let i = 0; i < reversedArray.length; i++) {
    // Multiply odd iterations by 2
    if (i % 2 === 0) {
      reversedArray[i] *= 2;
      // Subtract 9 from 2 digit numbers
      if (reversedArray[i] > 9) {
        reversedArray[i] -= 9;
      }
    }
    sum += reversedArray[i];
  }
  // Check if number is divisible by 10
  return (sum + droppedNum) % 10 === 0;

}
```

Once the loop is complete, the `droppedNum` variable is added to the total of `sum`. Using the modulus operator `%`, `sum` is then return as a truthy value if it is divisible by 10, otherwise `false` is returned.
``` 
// Check if number is divisible by 10
       return (sum + droppedNum) % 10 === 0;
 ```` 
 
 This completes the function.

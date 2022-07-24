# 1. Odd or Even

**Kata Link:** https://www.codewars.com/kata/5949481f86420f59480000e7

**Description:** Given a list of integers, determine whether the sum of its elements is odd or even.

Give your answer as a string matching "odd" or "even".

If the input array is empty consider it as: [0] (array with a zero).

**Example**

![image](https://user-images.githubusercontent.com/45276763/179884010-94fb9901-c16a-4ad8-9c61-986e723fc8e1.png)

## `My Solutions`
```JavaScript
/* OPTION 1 */
function oddOrEven(array) {
  if( array.length === 0 ) return 'even'; // checking the array length
  
   const result = array.reduce((prev, curr ) => prev + curr ); // getting the sum of all the elements in the array
  
  return result % 2 === 0 ? 'even' : 'odd'; // checking if the result is even or odd
}

/* OPTION 2 */
function oddOrEven(array) {
  const result = array.reduce((prev, curr ) => prev + curr, 0 ); // getting the sum of all the elements in the array
  return result % 2 === 0 ? 'even' : 'odd'; // checking if the result is even or odd
}


/* OPTION 3*/
function oddOrEven(array) {  //getting the sum of all the elements in the array and checking if the result is even or odd
  return array.reduce((prev, curr ) => prev + curr, 0 ) % 2 === 0 ? 'even' : 'odd';
}

```

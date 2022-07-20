# 1. Odd or Even

**Kata Link:** https://www.codewars.com/kata/5949481f86420f59480000e7

**Description:** Given a list of integers, determine whether the sum of its elements is odd or even.

Give your answer as a string matching "odd" or "even".

If the input array is empty consider it as: [0] (array with a zero).

**Example**

![image](https://user-images.githubusercontent.com/45276763/179884010-94fb9901-c16a-4ad8-9c61-986e723fc8e1.png)

## `My Solutions`
```JavaScript
function oddOrEven(array) {
  if( array.length === 0 ) return 'even';
  
   const result = array.reduce((prev, curr ) => prev + curr );
  
  return result % 2 === 0 ? 'even' : 'odd'
}
```

```JavaScript
function oddOrEven(array) {
  const result = array.reduce((prev, curr ) => prev + curr, 0 );
  return result % 2 === 0 ? 'even' : 'odd'
}
```

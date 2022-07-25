# 1. Is Palindrome? / Palindrome strings

**Kata Link:** https://www.codewars.com/kata/57a5015d72292ddeb8000b31

**Description:** A palindrome is a word, phrase, number, or other sequence of characters which reads the same backward or forward. 
This includes capital letters, punctuation, and word dividers.

Implement a function that checks if something is a palindrome. If the input is a number, convert it to string first.

For example **(Input ==> Output)**

![image](https://user-images.githubusercontent.com/45276763/180698171-ad7fb8de-34b5-4a65-9a62-aa1079f5f18e.png)

## `My Solution`

```JavaScript
function isPalindrome(line) {
  // making the line toString if the input is a number
  //split the string for reverse the array and then joining the string again
  return line.toString() === line.toString().split('').reverse().join('');
}
```

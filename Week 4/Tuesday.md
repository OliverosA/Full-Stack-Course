# 1. Leap Years

**Kata Link:** https://www.codewars.com/kata/526c7363236867513f0005ca/train/javascript

**Description:** In this kata you should simply determine, whether a given year is a leap year or not. 
In case you don't know the rules, here they are:

 * years divisible by 4 are leap years
* but years divisible by 100 are not leap years
* but years divisible by 400 are leap years

Additional Notes:

Only valid years (positive integers) will be tested, so you don't have to validate them

## `My Solutions`

```JavaScript
function isLeapYear(year) {
  if ( year % 400 === 0 ) return true;
  if ( year % 100 === 0 ) return false;
  if ( year % 4 === 0 ) return true;
  return false
}

function isLeapYear(year) {
  if ( year % 400 === 0 ) return true;
  if ( year % 100 === 0 ) return false;
  return ( year % 4 === 0 );
}
```

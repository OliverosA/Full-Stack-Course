# 1. Smallest Integer In Array / Find the smallest integer in the array

**Kata Link:** https://www.codewars.com/kata/55a2d7ebe362935a210000b2

**Description:** Given an array of integers your solution should find the smallest integer.

For example:

* Given [34, 15, 88, 2] your solution will return 2
* Given [34, -345, -1, 100] your solution will return -345

You can assume, for the purpose of this kata, that the supplied array will not be empty.

## `My Solutions`
```JavaScript

//Option 1
class SmallestIntegerFinder {
    findSmallestInt(args) {
        return args.reduce(
        ( prev, curr ) => Math.min( prev, curr ));
    }
}

//Option 2
class SmallestIntegerFinder {
  findSmallestInt(args) {
    return Math.min(...args);
  }
}
```

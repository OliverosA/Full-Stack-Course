# 1. Two To One

**Kata Link:** https://www.codewars.com/kata/5656b6906de340bd1b0000ac/train/javascript

**Description:** Take 2 strings s1 and s2 including only letters from a to z. 
Return a new sorted string, the longest possible, containing distinct letters - each taken only once - coming from s1 or s2.

**Example**

![image](https://user-images.githubusercontent.com/45276763/183543352-56f4f040-3aa3-4da8-8241-cc3ba8a6cb48.png)

## `My Solution`

```JavaScript
function longest(s1, s2) {
  const s3 = (s1 + s2).split('').sort();
  let result = new Set(s3);
  return [...result].join('');
}
```

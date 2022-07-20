# 1. Ensure Question

**Kata Link:** https://www.codewars.com/kata/5866fc43395d9138a7000006

**Description:** Given a string, write a function that returns the string with a question mark ("?") 
appends to the end, unless the original string ends with a question mark, in which case, 
returns the original string.

For example **(Input --> Output)**

![week1EnsureQuestion](https://user-images.githubusercontent.com/45276763/179870242-f5179603-2c6b-4944-bdb9-c3a19e2955b9.png)

## `My Solution`
```JavaScript
function ensureQuestion(s) {
    return s.endsWith('?') ? s : s + '?';
}
```

# 2. Reverse Sentence / Reversed Words

**Kata Link:** https://www.codewars.com/kata/51c8991dee245d7ddf00000e

**Description:** Complete the solution so that it reverses all of the words within the string passed in.

For example **(Input --> Output):**

![image](https://user-images.githubusercontent.com/45276763/179870759-3519f9c9-d438-414d-95a4-bde2c87bc08b.png)

## `My Solution`
```JavaScript
function reverseWords(str){
    return str
        .split(' ')
        .reverse()
        .join(' ');
}
```

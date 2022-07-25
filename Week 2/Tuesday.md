# 1. Well Of Ideas / Well of Ideas

**Kata Link:** https://www.codewars.com/kata/57f222ce69e09c3630000212

**Description:** For every good kata idea there seem to be quite a few bad ones!

In this kata you need to check the provided array (x) for good ideas 'good' and bad ideas 'bad'. 
If there are one or two good ideas, return 'Publish!', if there are more than 2 return 'I smell a series!'. 
If there are no good ideas, as is often the case, return 'Fail!'.

## `My Solution`

```JavaScript
function well(x){
  const result = x.filter(word => word === 'good'); // filter the array
  
  // evaluating if the array obtained by the filter is greater than or equal to 3
  if ( result.length >= 3 ) return 'I smell a series!'; 
  
  return ( result.length === 0 ? 'Fail!' : 'Publish!');
}


// Interesting Kata Solution (not my solution but a love it!)
function well(x){
  const result = x.filter(word => word === 'good').length;
  
  return result < 1 ? 'Fail!' :
         result < 3 ? 'Publish!' : 'I smell a series!';
}

```

# Functon

---

## Task-10:Write a function to find longest substring in a given a string withoutrepeating characters except space character. If there are several,return the last one. Considerthat all letters are lowercase.

```javascript
function getLongestSubstring(str) {
  let longestStr = "";
  let counter = str[0];
  for (let i = 1; i < str.length; i++) {
    if (counter.indexOf(str[i]) === -1 || str[i] === " ") {
      counter += str[i];
      continue;
    }
    if (longestStr.length <= counter.length) {
      longestStr = counter;
      i = i - counter.length;
      counter = "";
    } else {
      i = i - counter.length;
      counter = "";
    }
  }
  return longestStr;
}
console.log(
  getLongestSubstring(
    'there are no two words in the english language more harmful than "good job".'
  )
);
```

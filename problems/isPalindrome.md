## Number Palindrome

Given an integer x, return true if x is palindrome integer.

An integer is a palindrome when it reads the same backward as forward.

For example, 121 is a palindrome while 123 is not.

```ts
Input: x = 121
Output: true
Explanation: 121 reads as 121 from left to right and from right to left.
```

```ts
function isPalindrome(x: number): boolean {
  const str: string = x.toString();
  const arr: string[] = str.split("");
  const revArr: string[] = arr.reverse();
  if (arr === revArr) {
    return true;
  } else {
    return false;
  }
}
```

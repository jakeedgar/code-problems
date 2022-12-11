## Two Sums [easy]

Given an array of integers n and an integer t, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

```ts
const twoSum = function (n: number[], t: number): number[] {
  let map = new Map();
  for (let i = 0; i < n.length; i++) {
    let complement = t - n[i];
    if (map[complement] !== undefined) {
      return [map[complement], i];
    }
    map[n[i]] = i;
  }
};
```

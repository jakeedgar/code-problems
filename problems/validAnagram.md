## Valid Anagram [easy]

Given two strings s and t, write a function or algorithm to determine if t is an anagram of s.

For example:

Input: s = "anagram", t = "nagaram"
Output: true

Input: s = "rat", t = "car"
Output: false

```ts
function isAnagram(s: string, t: string): boolean {
    if (s.length !== t.length) {
        return false;
    }

    const charCount: Map<string, number> = new Map();

    // Count characters in string s
    for (const char of s) {
        charCount.set(char, (charCount.get(char) || 0) + 1);
    }

    // Decrement character counts for string t
    for (const char of t) {
        if (!charCount.has(char)) {
            return false; // A character is missing in s
        }
        charCount.set(char, charCount.get(char)! - 1);
        if (charCount.get(char)! === 0) {
            charCount.delete(char);
        }
    }

    return charCount.size === 0; // All characters have been matched and canceled out
}

// Test cases
console.log(isAnagram("anagram", "nagaram")); // Output: true
console.log(isAnagram("rat", "car"));         // Output: false
```
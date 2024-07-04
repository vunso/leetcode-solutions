## [125. Valid Palindrome](https://leetcode.com/problems/valid-palindrome/description/)

### Problem
A phrase is a **palindrome** if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward. Alphanumeric characters include letters and numbers.

Given a string `s`, return `true` if it is a **palindrome**, or `false` otherwise.

<p><strong class="example">Example 1:</strong></p>

<pre>
<strong>Input:</strong> s = &quot;A man, a plan, a canal: Panama&quot;
<strong>Output:</strong> true
<strong>Explanation:</strong> &quot;amanaplanacanalpanama&quot; is a palindrome.
</pre>

<p><strong class="example">Example 2:</strong></p>

<pre>
<strong>Input:</strong> s = &quot;race a car&quot;
<strong>Output:</strong> false
<strong>Explanation:</strong> &quot;raceacar&quot; is not a palindrome.
</pre>

<p><strong class="example">Example 3:</strong></p>

<pre>
<strong>Input:</strong> s = &quot; &quot;
<strong>Output:</strong> true
<strong>Explanation:</strong> s is an empty string &quot;&quot; after removing non-alphanumeric characters.
Since an empty string reads the same forward and backward, it is a palindrome.
</pre>

### Constraints:

- `1 <= s.length <= 2 * 105`
- `s` consists only of printable ASCII characters.
---

### Approach

Pattern: Two Pointers

We use two pointers $i$ and $j$ to point to the two ends of the string $s$, and then loop through the following process until `i < j`

1. If $s[i]$ is not a letter or a number, move the pointer $i$ one step to the right and continue to the next loop.
2. If $s[j]$ is not a letter or a number, move the pointer $j$ one step to the left and continue to the next loop.
3. If the lowercase form of $s[i]$ and $s[j]$ are not equal, return `false` and move the pointer $i$ one step to the right and the pointer $j$ one step to the left, and continue to the next loop.

At the end of the loop, return `true`.

The time complexity is $O(n)$, where $n$ is the length of the string $s$. The space complexity is $O(1)$.


### Solution

```cpp
class Solution {
public:
    bool isPalindrome(string s) {
        int i = 0, j = s.length() - 1;
        while(i < j) {
            if (!isalnum(s[i])) i++; //ignore alphanumeric on left side
            else if (!isalnum(s[j])) j--; //ignore alphanumeric on right side
            else if(tolower(s[i++]) != tolower(s[j--])) return false;
        }
        return true;
    }
};
```
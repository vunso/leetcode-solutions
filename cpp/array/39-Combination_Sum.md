## [39. Combination Sum](https://leetcode.com/problems/combination-sum/description/)

### Problem

Given an array of **distinct** integers candidates and a `target` integer target, return a list of all **unique combinations** of `candidates` where the chosen numbers sum to `target`. You may return the combinations in **any order**.

The **same** number may be chosen from `candidates` an **unlimited number** of times. Two combinations are unique if the 
frequency
 of at least one of the chosen numbers is different.

The test cases are generated such that the number of unique combinations that sum up to `target` is less than `150` combinations for the given input.


<p><strong class="example">Example 1:</strong></p>
<pre>
<strong>Input: </strong>candidates = <code>[2,3,6,7], </code>target = <code>7</code>
<strong>Output: </strong>[[2,2,3],[7]]
<strong>Explanation:</strong>
2 and 3 are candidates, and 2 + 2 + 3 = 7. Note that 2 can be used multiple times.
7 is a candidate, and 7 = 7.
These are the only two combinations.
</pre>

<p><strong class="example">Example 2:</strong></p>
<pre>
<strong>Input: </strong>candidates = [2,3,5]<code>, </code>target = 8
<strong>Output: </strong>[[2,2,2,2],[2,3,3],[3,5]]
</pre>

<p><strong class="example">Example 3:</strong></p>
<pre>
<strong>Input: </strong>candidates = <code>[2], </code>target = 1
<strong>Output: </strong>[]
</pre>

### Constraints:

- `1 <= candidates.length <= 30`
- `2 <= candidates[i] <= 40`
- All elements of `candidates` are distinct
- `1 <= target <= 40`
---

### Approach

TBU

### Solution
```cpp
class Solution {
public:
    void findCombination(vector<int> &arr, int target, int index, vector<int> &list, vector<vector<int>> &ans)
    {
        if(index == arr.size()) {
            if(target == 0)
                ans.push_back(list);
            return;
        }
        // Pick case
        if(arr[index] <= target) {
            list.push_back(arr[index]);
            findCombination(arr, target - arr[index], index, list, ans);
            list.pop_back();
        }
        // Non-pick case
        findCombination(arr, target, index + 1, list, ans);

    }
    vector<vector<int>> combinationSum(vector<int>& candidates, int target) {
     vector<vector<int>> ans;
     vector<int> list;
     findCombination(candidates, target, 0, list, ans);
     return ans;
    }
};
```
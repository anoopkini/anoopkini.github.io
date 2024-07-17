---
title: "LC#242: Valid Anagram : LeetCode solution : Python"
layout: post
categories: interview-prep data-structures
lcUrl: https://leetcode.com/problems/valid-anagram/
ncUrl: https://www.youtube.com/watch?v=9UtInBqnCgA
ghRepo: lc-problems
ghPath: 242-valid-anagram.py
problem_title: "Valid Anagram"
modified_date: 2024-07-15
tags: python hashMap leetcode-solutions
---
**Description:** *Given two strings `s` and `t`, return `true` if `t` is an anagram of `s`, and `false` otherwise.*

<!--more-->

*Example 1:*

Input : `s = "anagram", t = "nagaram"`
Output: `true`

*Example 2:*

Input : `s = "rat", t = "car"`
Output: `false`
 
**Constraints:**

- 1 <= s.length, t.length <= 5 * 10<sup>4</sup>

- s and t consist of lowercase English letters.

## Solution

### *Brute Force*: 

- Find count of each character. If the count is same then they match. 
- Time: O(S+T) &rarr; time to loop over the string to build the map.
- Space: O(S+T) &rarr; space of the two hash maps

{% include ghCodeBlock.html highlight="python" repo=page.ghRepo filepath=page.ghPath lcurl=page.lcUrl %}

### *Revised Solution*:
We can revise this solution to improve the space complexity to O(1) *Assumption: Sorting algo's dont need additional extra memory*
- Once sorted both strings should be equal. 
- Time: O(S+T)
- Space: O(1)

``` python
    return sorted(s) == sorted(t)
```

{% include lc-nc-block.html lcUrl=page.lcUrl ncUrl=page.ncUrl problem_title=page.problem_title %}
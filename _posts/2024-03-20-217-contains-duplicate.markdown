---
title: LC#217: Contains Duplicates
layout: post
category: DataStructures
---

**Description:** *Given an integer array nums, return true if any value appears at least twice in the array, and return false if every element is distinct.*

*Example 1:*

Input : `nums = [1,2,3,1]`
Output: `true`

*Example 2:*

Input : `nums = [1,2,3,4]`
Output: `false`

*Example 3:*

Input: `nums = [1,1,1,3,3,4,3,2,4,2]`
Output: `true`
 
**Constraints:**

- 1 <= nums.length <= 10<sup>5</sup>
- -10<sup>9</sup> <= nums[i] <= 10<sup>9</sup>

## Solution

### *Brute Force*: 

- Compare every element of the array with other elements. Return true if two elements are same else return false. 
- Time: `O(n^2)` -> for every elements the whole array is iterated making it n*n
- Space: `O(1)` -> no additional memory

``` python
for i in range(len(nums)-1):
    for j in range(i+1, len(nums)):
        if nums[i] == nums[j]:
            return True
return False
```

### *Revised Solution*:
- Sort the array. Return true if two adjacent elements are same, else return false.
- Time: `O(n.log(n))` -> single loop of the array + time complexity of the sorting algo
- Space: `O(1)` -> No additional memory

``` python
for i in range(len(sorted_nums)-1):
    for j in range(i+1, len(sorted_nums)):
        if sorted_nums[i] == sorted_nums[j]:
            return True
return False
```

### *Optimal Solution*:
- As you are looping through the array add it to a hash set.
- Time: `O(n)` -> single loop of the array
- Space: `O(n)` -> space occupied by hastset

{% include ghCodeBlock.html highlight="python" repo="lc-problems" filepath="217-contains-duplicate.py" lcurl="https://leetcode.com/problems/contains-duplicate/" %}
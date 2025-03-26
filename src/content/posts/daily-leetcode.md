---
title: LeetCode 每日一题
published: 2025-03-25
description: 每天刷一道力扣
image: ../../assets/images/cover2.jpg
tags:
  - leetcode
category: Career Journal
draft: false
lang: en
---
## 2025-03-26

> [438. 找到字符串中所有字母异位词 - 力扣（LeetCode）](https://leetcode.cn/problems/find-all-anagrams-in-a-string/description)

很典的滑动窗口，导致我的做法和官方题解几乎一样……

```python
class Solution:
    def findAnagrams(self, s: str, p: str) -> List[int]:
        len_s, len_p = len(s), len(p)

        ans = []
        if len_s >= len_p:
            s_count = [0] * 26
            p_count = [0] * 26
            for i in range(len_p):
                s_count[ord(s[i]) - 97] += 1
                p_count[ord(p[i]) - 97] += 1
    
            if s_count == p_count:
                ans.append(0)
    
            for i in range(len_s - len_p):
                s_count[ord(s[i]) - 97] -= 1
                s_count[ord(s[i + len_p]) - 97] += 1
                
                if s_count == p_count:
                    ans.append(i + 1)

        return ans    
```
## 2025-03-25

> [3. 无重复字符的最长子串 - 力扣（LeetCode）](https://leetcode.cn/problems/longest-substring-without-repeating-characters/)

从无重复字符，可以想到用 set 的数据结构维护一个子串所包含的所有字符，并用于查询新字符是否已经存在；然后用双指针记录当前子串左右边界，并且注意到每次左指针向右移动后，右指针一定是“不减”的。

```python
class Solution:
    def lengthOfLongestSubstring(self, s: str) -> int:
        l: int = 0
        r: int = 1
        max_l = 0
        chars = set()
        for l in range(len(s)):
            if not l == 0:
                chars.discard(s[l - 1])
            chars.add(s[l])
            r = max(l + 1, r)
            while r < len(s):
                if not s[r] in chars:
                    chars.add(s[r])
                    r += 1
                else:
                    break
            max_l = max(max_l, r - l)
        return max_l
```

## 2025-03-24

> [15. 三数之和 - 力扣（LeetCode）](https://leetcode.cn/problems/3sum/description/)

主要思路：先排序，然后双指针移动

```python
class Solution:
    def check(self, i: int, j: int, k: int, nums: List[int]):
        return nums[i] + nums[j] + nums[k] == 0
    def threeSum(self, nums: List[int]) -> List[List[int]]:
        nums = sorted(nums)
        ans = []
        for i in range(len(nums) - 2):
            if i == 0 or nums[i] != nums[i - 1]:
                k = len(nums) - 1
                for j in range(i + 1, len(nums)):
                    if j == i + 1 or nums[j] != nums[j - 1]:
                       while k > j and nums[i] + nums[j] + nums[k] > 0:
                           k -= 1
                       if k == j:
                           continue
                       if self.check(i, j, k, nums):
                          ans.append([nums[i], nums[j], nums[k]])
        return ans
```

---

> [42. 接雨水 - 力扣（LeetCode）](https://leetcode.cn/problems/trapping-rain-water/)

考虑到每一个位置能存储的水量和左右两边的最高高度，以及自身的高度相关，所以先遍历一遍用 dp 算出来，最后累加答案即可。

```python
class Solution:
    def single_trap(self, height: int, max_l: int, max_r: int):
        if height >= max_l or height >= max_r:
            return 0
        else:
            return min(max_l, max_r) - height
    def trap(self, height: List[int]) -> int:
        max_l_height = [0] * len(height)
        max_r_height = [0] * len(height)
        for i in range(1, len(height)):
            max_l_height[i] = max(max_l_height[i - 1], height[i - 1])
            max_r_height[len(height) - 1 - i] = max(height[len(height) - i], max_r_height[len(height) - i])
        ans = 0
        for i in range(len(height)):
            ans += self.single_trap(height[i], max_l_height[i], max_r_height[i])
        return ans
```

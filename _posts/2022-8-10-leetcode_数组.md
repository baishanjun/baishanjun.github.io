---
layout:     post
title:      leetcode--数组
subtitle:   数组
date:       2022-08-10
author:     孔润
header-img: img/the-first.png
catalog:   true
tags:
    - leetcode
---
# 数组基础题目
------------------------------------------------------------
## 数组操作
-----------------------------------------------------------
##### 题号：0189&emsp;&emsp;标题：[轮转数组](https://leetcode.cn/problems/rotate-array/)
- 给你一个数组，将数组中的元素向右轮转 k 个位置，其中 k 是非负数。
<font size=3>示例1：</font>
```
输入: nums = [1,2,3,4,5,6,7], k = 3
输出: [5,6,7,1,2,3,4]
解释:
向右轮转 1 步: [7,1,2,3,4,5,6]
向右轮转 2 步: [6,7,1,2,3,4,5]
向右轮转 3 步: [5,6,7,1,2,3,4]
```
<font size=3>示例2:</font>
```
输入：nums = [-1,-100,3,99], k = 2
输出：[3,99,-1,-100]
解释: 
向右轮转 1 步: [99,-1,-100,3]
向右轮转 2 步: [3,99,-1,-100]
```
<font size=3>题解:</font>
- 将数组分为两段处理：对k进行数组长度的取余(k%len(nums)),得到的数就是数组后半段需要移动到前面的个数，即[-k:],最后可得到所求的数组为[-k:]+[:-k]
（切片操作可以参考流畅python第二章）
```
class Solution:
    def rotate(self, nums: List[int], k: int) -> None:
        """
        Do not return anything, modify nums in-place instead.
        """
        n = len(nums)
        k = k % n
        nums[:] = nums[-k:]+nums[:-k]
```

-------------------------------------

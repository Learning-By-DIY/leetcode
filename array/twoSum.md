# problem

Given an array of integers, return indices of the two numbers such that they add up to a specific target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

Example:

```
Given nums = [2, 7, 11, 15], target = 9,

Because nums[0] + nums[1] = 2 + 7 = 9,
return [0, 1].
```



# ideas

1. 申明一个map用于查询
2. 遍历数组元素，**固定**遍历得到的元素，在map中寻找差值
3. map中没有差值，把固定的元素作为差值的角色放入map用来和别的元素进行匹配
4. map有差值，寻找到对应的结果



# code

```
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        map = dict()
        for index, data in enumerate(nums):
            other = target - data
            if other in map:
                return map[other],index
            map[data] = index
        return []
```



# key point

1. 两数之和，固定一个值寻找下一个值
2. 寻找元素可以用map, map的值动态填充




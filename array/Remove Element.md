# problem

Given an array nums and a value val, remove all instances of that value in-place and return the new length.

Do not allocate extra space for another array, you must do this by modifying the input array in-place with O(1) extra memory.

The order of elements can be changed. It doesn't matter what you leave beyond the new length.

Example 1:

```
Given nums = [3,2,2,3], val = 3,

Your function should return length = 2, with the first two elements of nums being 2.

It doesn't matter what you leave beyond the returned length.
```


Example 2:

```
Given nums = [0,1,2,2,3,0,4,2], val = 2,

Your function should return length = 5, with the first five elements of nums containing 0, 1, 3, 0, and 4.

Note that the order of those five elements can be arbitrary.

It doesn't matter what values are set beyond the returned length.
```



# ideas

和 Remove Duplicates from Sorted Array 思路一致，都是采用双指针。只不过这里比较的条件不再是nums[i]和nums[j]进行比较，而是nums[i]和固定的value进行比较



# code

```
class Solution:
    def removeElement(self, nums: List[int], val: int) -> int:
        new_idx = 0
        
        for i in range(len(nums)):
            if nums[i] != val:
                nums[new_idx] = nums[i]
                new_idx += 1
        
        return new_idx
```



# key point

**双指针**






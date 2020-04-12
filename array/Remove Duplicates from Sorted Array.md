# problem

Given a sorted array nums, remove the duplicates in-place such that each element appear only once and return the new length.

Do not allocate extra space for another array, you must do this by modifying the input array in-place with O(1) extra memory.

Example 1:

```
Given nums = [1,1,2],

Your function should return length = 2, with the first two elements of nums being 1 and 2 respectively.

It doesn't matter what you leave beyond the returned length.
```


Example 2:

```
Given nums = [0,0,1,1,1,2,2,3,3,4],

Your function should return length = 5, with the first five elements of nums being modified to 0, 1, 2, 3, and 4 respectively.

It doesn't matter what values are set beyond the returned length.
```



# ideas

1. **双指针**, 设立两个指针分别为 i 和 j
2. 指针i: 去重之后的元素应该存储的位置
3. 指针j: 下一个需要审查的元素
4. nums[i] != nums[j]：找到去重后的一个元素，对这个元素进行操作放到应该放的位置



# code

```go
func removeDuplicates(nums []int) int {
    if len(nums) == 0 {
        return 0
    }
    i := 0
    for j := 1; j < len(nums); j++ {
        if nums[i] != nums[j] {
            i++
            nums[i] = nums[j]
        }
    }
    return i + 1
}
```





# key ponit

1. 双指针
2. 定义指针应有的含义，后续代码操作维护指针含义




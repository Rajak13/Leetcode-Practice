## 1. Given an integer array nums, if any numbers appears twice, return true, else return false

**i.Brute Force**

For this easy problem, we can use various methods. First would be Brute Force which would just go through each elemnet of the array,check if a number is repeated twice and then return true or false depending on the situtaion. However, the time complexity for this woukd be O(n^2) which is not optimal.

**ii.Sorting**

A better method would be sorting where we first sort all the elments in order so that duplicate values(if they exist) get placed next to each other causing us to have a much better time complexity.

```python
def containsDuplicate(nums):
    nums.sort()  # O(n log n)
    for i in range(1, len(nums)):
        if nums[i] == nums[i - 1]:
            return True
    return False

```

**iii.Using Hashset**

This method is the best approach as it allows us to compare thge array with our hashset i.e. we have an empty hashset at first and as we iterate through the array we add the numbers in the hashset, whenever we encounter a number that is already in the hashset, we can return true, else false.

```python
def containsDuplicate(nums):
    seen = set()

    for num in nums:
        if num in seen:
            return True
        seen.add(num)
    return False
```
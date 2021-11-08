# 二分查找法-查找target特定元素
---
---

```java
class Solution {
    public int search(int[] nums, int target) {
        int left = 0;
        int right = nums.length;
        while(left < right){
            int mid = left +(right-left)/2;
            if(nums[mid] == target){
                return mid;
            }
            if(nums[mid]<target){
                left = mid+1;
            }
            if(nums[mid]>target){
                right = mid;
            }
        }
        return -1;
    }
}
```


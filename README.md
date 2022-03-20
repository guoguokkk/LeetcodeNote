# LeetcodeNote
每日一题

## 二分查找
https://leetcode.com/problems/search-insert-position/

```c++
class Solution {
public:
    int searchInsert(vector<int>& nums, int target) {
        int start = 0;
        int end = nums.size()-1;
        if(nums.size()==0 || nums[0]>target)
            return 0;
        if(nums[end]<target)
            return end+1;
        
        int mid = (end-start)/2+start;
        while(start<=end){
            if (nums[mid] == target){
                break;
            }else if (nums[mid] < target){
                start = mid+1;
            }else{
                end = mid-1;
            }
            mid = (end-start)/2+start;
        }
        
        return mid;
    }
};
```

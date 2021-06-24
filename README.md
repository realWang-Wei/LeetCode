# LeetCode刷题记录


## 剑指offer15.二进制中1的个数
链接:[Link](https://leetcode-cn.com/problems/er-jin-zhi-zhong-1de-ge-shu-lcof/submissions/)


Solutin:如果一位一位的遍历32次，如果n的高位有很多0，这种做法无疑会浪费时间，所以，使用下面的方法可以只遍历到最高位的1

```C++
class Solution {
   public:
     int hammingWeight(uint32_t n) {
         int ret = 0;
         while(n != 0){
             ret += (n & 1);
             n = n >> 1;
         }
         return ret;
     }
   };
```

## 27.移除元素
使用双指针
```c++
class Solution {
public:
    int removeElement(vector<int>& nums, int val) {
        int n = nums.size();  // 数组长度
        int left=0;
        for(int right = 0; right < n; right++){
            if(nums[right] != val){
                nums[left] = nums[right];
                left++;
            }

        }
        return left;
    }
};
```

## 35.搜索插入位置
暴力法
```c++
class Solution {
public:
    int searchInsert(vector<int>& nums, int target) {
        int n = nums.size();
        for(int i=0;i<n;i++){
            if(nums[i] >= target) return i;
        }
        return n;
    }
};
```

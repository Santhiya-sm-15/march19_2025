# march19_2025
The problem that i solved today in leetcode

1.You are given a binary array nums.

You can do the following operation on the array any number of times (possibly zero):

Choose any 3 consecutive elements from the array and flip all of them.
Flipping an element means changing its value from 0 to 1, and from 1 to 0.

Return the minimum number of operations required to make all elements in nums equal to 1. If it is impossible, return -1.

Code:
class Solution {
    public int minOperations(int[] nums) {
        int n=nums.length;
        int cnt=0;
        for(int i=0;i<n-2;i++)
        {
            if(nums[i]==0)
            {
                nums[i]=1-nums[i];
                nums[i+1]=1-nums[i+1];
                nums[i+2]=1-nums[i+2];
                cnt++;
            }
        }
        if(nums[n-1]==1 && nums[n-2]==1)
            return cnt;
        return -1;
    }
}

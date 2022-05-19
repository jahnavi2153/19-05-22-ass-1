# 19-05-22-ass-1
class Solution:
    def subarraySum(self, nums: List[int], k: int) -> int:
        n=len(nums)
        if n==0:
            return 0
        count=0
        dic={}
        curr_sum=0
        for i in range(n):
            curr_sum+=nums[i]
            if(curr_sum==k):
                count+=1
            if(curr_sum-k in dic):
                count+=dic[curr_sum-k]
            if(curr_sum in dic):
                dic[curr_sum]+=1
            else:
                dic[curr_sum]=1
        return count
        
output:
Your input:[1,1,1]
           2
output: 2
Expected: 2

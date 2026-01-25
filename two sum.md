## leetcode east two sum #hash map
### 暴力解
'''[r]
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        int length = nums.size();
        for(int i = 0 ; i < length-1 ; i++){
            for(int j = i+1 ; j< length ; j++){
                if(target == nums[i]+nums[j]) 
                    return vector<int>{i,j};
            }
        }
        return {};
    }
};
'''

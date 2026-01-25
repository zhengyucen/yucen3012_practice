## leetcode east two sum #hash map
Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
### 暴力解
```{r}
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
```
### 使用hash map
```{r}
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        int length = nums.size();
        unordered_map <int , int> map_test; //hashmap 
        for(int i = 0 ; i < length ; i++){
            int a = target - nums[i];
            if(map_test.count(a) > 0) { //看看map中有沒有目標數,沒有就存入map
                return vector<int> {i,map_test[a]};
            }
            map_test[nums[i]] = i;
        }
        return {};
    }
};
```
#### hash map
unordered_map 和 map
差別在於有沒有序列,map像圖書館都編號擺好
複雜度分別是O(1)和O(log)
hashmap用在知道要找目標的名子
如果只是要純範圍 用MAP更好

使用上不能用 map["Alice"] == 100 因為如果沒找到 他會創造一個ALICE給0
要用map.find("Alice") != map.end()
沒找到會回傳map.end() (邊界牆)

##### 額外知識點
```{r}
auto it = myMap.find("Ghost");
if (it == myMap.end()) {
cout << "find 沒找到 Ghost" << endl;
}
```
auto > c++ 11 的東西 一定要代數值,能自動判斷數值類型
it 

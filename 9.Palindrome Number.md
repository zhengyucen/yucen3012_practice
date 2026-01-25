## leetcode 9 easy Palindrome Number
Example 1:

Input: x = 121
Output: true
Explanation: 121 reads as 121 from left to right and from right to left.
### 暴力迴圈解(用while去一一比對)(時間最快10.9mb , 0ms)
```{r}
class Solution {
public:
    bool isPalindrome(int x) {
        string a = to_string(x);
        int i = 0;
        int j = size(a)-1;
        while(j>i){
            if(a[j] != a[i]) return false;
            i++;
            j--; 
        }
        return true;
    }
};
```
### string反轉解(11mb , 4ms)
```{r}
class Solution {
public:
    bool isPalindrome(int x) {
        string str;
        string str2;
        str=to_string(x);
        str2=str;
        reverse(str.begin(),str.end()); //將str 從頭(.begin())到尾翻轉
        if(str==str2){
            return true;
        }else{
           return false;
        }
    }
};
```
### 省空間數字解(8.5mb , 3ms)
# 透過數字用%10將數字一個個翻轉,轉一半然後比對
```{r}
class Solution {
public:
    bool isPalindrome(int x) {
        if(x < 0 || (x % 10 == 0 && x != 0)) return false; //先將負號和0移出 怕出現 10翻轉後 01 
        int rever_num = 0;
        while(x > rever_num){
            rever_num = rever_num*10 + x%10;
            x /= 10;
        }
        return rever_num == x || rever_num/10 == x;
    }
};
```

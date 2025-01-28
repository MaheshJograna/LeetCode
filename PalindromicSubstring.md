# 647. Palindromic Substrings
### Problem:
https://leetcode.com/problems/palindromic-substrings/description/?envType=problem-list-v2&envId=oizxjoit&
### Reference:
https://www.youtube.com/watch?embeds_referring_euri=https%3A%2F%2Fleetcode.com%2F&source_ve_path=MTY0OTksMjg2NjQsMTY0NTAz&v=vm6HKRHB7n0&feature=youtu.be
### Solution:
```c
class Solution {
public:
    int countSubstrings(string s) {
        int n = s.length(), ans = 0;
        for(int i = 0; i<n ; ++i){
            int even = expandfromCentre(s, i, i+1);
            int odd = expandfromCentre(s,i ,i);
            ans += even + odd;
        }
        return ans;
    }
    int expandfromCentre(const string& s, int left, int right){
    int count = 0;
    while(left >= 0 && right < s.length() && s[left]== s[right])
    {
        --left;
        ++right;
        ++count;
    }
    return count;}
};

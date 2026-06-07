// 1. two sum
class Solution {
public
    vector<int> twoSum(vector<int>& nums, int target) {
        unordered_map<int, int> mp; // value -> index
 for (int i = 0; i < nums.size(); i++) {
            int complement = target - nums[i];
if (mp.find(complement) != mp.end()) {
                return {mp[complement], i};
            }
mp[nums[i]] = i;
        }

return {};
    }
};

 //2. Remove Duplicate from sorted array
class Solution {
public:
    int removeDuplicates(vector<int>& nums) {
        if (nums.empty()) return 0;

int k = 1; 
        for (int i = 1; i < nums.size(); i++) {
            if (nums[i] != nums[i - 1]) {
                nums[k] = nums[i];
                k++;
            }
        }
//3. Best time to sell and buy a stock
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int minPrice = INT_MAX;
        int maxProfit = 0;

for (int price : prices) {
            minPrice = min(minPrice, price);
            maxProfit = max(maxProfit, price - minPrice);
        }
 return maxProfit;
    }
};
        return k;
    }
};
//

//DAY 2
//1.maximum subarray
class Solution {
public:
    int maxSubArray(vector<int>& nums) {
        int sum=0;
        int maxi=INT_MIN;
        for(int i=0;i<nums.size();i++){
            sum+=nums[i];
            maxi=max(maxi,sum);
            if(sum<=0){
                sum=0;
            }
        }
        return maxi;
    }
};
//2.conatins Duplicate
class Solution {
public:
    bool containsDuplicate(vector<int>& arr) {
        sort(arr.begin(), arr.end());
        for (int i = 1; i < arr.size(); i++) {
            if (arr[i] == arr[i-1]) return true;  // duplicate
        }
        return false;
    }
};
//3. maximum average Subarray 1
class Solution {
public:
    double findMaxAverage(vector<int>& nums, int k) {
        int n=nums.size();
        double wsum=0;
        for(int i=0;i<k;i++){
            wsum+=nums[i];
        }
        double wavg=wsum/k;
        double avg=0;
      
double res=wavg;
        int i=0,j=k;
        while(j<n){
            wsum=wsum+nums[j]-nums[i];
                avg=wsum/k;
                res=max(res,avg);
                i++;
                j++;
        }
      
        return res;
    }
};

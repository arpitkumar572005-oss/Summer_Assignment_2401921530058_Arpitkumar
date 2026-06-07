//DAY 3
//1.MOVE ZEROS
class Solution {
public:
    void moveZeroes(vector<int>& arr) {
         int n=arr.size();
       int j=-1;
       for(int i=0;i<n;i++){
          if(arr[i]==0){
              j=i;
              break;
          }
       }
       if(j==-1){
           return ;
       }
       for(int i=j+1;i<n;i++){
           if(arr[i]!=0){
               swap(arr[i],arr[j]);
            j++;
               
           }
       }
    }
};

// 2.SQURE OF SORTED ARRAY
class Solution {
public:
    vector<int> sortedSquares(vector<int>& nums) {
        int n=nums.size();
        vector<int>ans(n);
        for(int i=0;i<n;i++){
            ans[i]=(nums[i]*nums[i]);
        }
        sort(ans.begin(),ans.end());
        return ans;
    }
};

//CONATINER WITH MOST WATER
class Solution {
public:
    int maxArea(vector<int>& height) {
        int left = 0;
        int right = height.size() - 1;
        int maxWater = 0;

        while (left < right) {
            int width = right - left;
            int currArea = min(height[left], height[right]) * width;

            maxWater = max(maxWater, currArea);

            if (height[left] < height[right]) {
                left++;
            } else {
                right--;
            }
        }

        return maxWater;
    }
};

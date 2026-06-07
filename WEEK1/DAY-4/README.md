//diagonal sum
class Solution {
public:
    int diagonalSum(vector<vector<int>>& mat) {
        int sum=0;
        int n=mat.size();
        for(int i=0;i<n;i++){
            for(int j=0;j<n;j++){
                if(i==j||i+j==n-1){
                    sum+=mat[i][j];
                }
            }
        }
        return sum;
    }
};

//spiral matrix
class Solution {
public:
    vector<int> spiralOrder(vector<vector<int>>& matrix) {
        int n=matrix.size();
        int m=matrix[0].size();
        int left=0,right=m-1;
        int top=0,bottom=n-1;
        vector<int>ans;
        while(left<=right&&top<=bottom){
        for(int i=left;i<=right;i++){
            ans.push_back(matrix[top][i]);
        }
        top++;
        for(int i=top;i<=bottom;i++){
            ans.push_back(matrix[i][right]);
        }
        right--;
        if(top<=bottom){
        for(int i=right;i>=left;i--){
            ans.push_back(matrix[bottom][i]);
        }
        bottom--;
        }
        if(left<=right){
        for(int i=bottom;i>=top;i--){
            ans.push_back(matrix[i][left]);
        }
        left++;
        }
    }
    return ans;
    }

    
 //reshape the matrix
    class Solution {
public:
    vector<vector<int>> matrixReshape(vector<vector<int>>& mat, int r, int c) {
        int m = mat.size();
        int n = mat[0].size();
 if (m * n != r * c)
            return mat;

   vector<vector<int>> ans(r, vector<int>(c));
        int row = 0, col = 0;

  for (int i = 0; i < m; i++) {
            for (int j = 0; j < n; j++) {
                ans[row][col] = mat[i][j];
                col++;
 if (col == c) {
                    col = 0;
                    row++;
                }
            }
        }

  return ans;
    }
};
};


//VALID PALINDROME
'''
class Solution {
public:
    bool isPalindrome(string s) {
        int left = 0, right = s.length() - 1;

 while (left < right) {
       
   while (left < right && !isalnum(s[left])) left++;
        while (left < right && !isalnum(s[right])) right--;

        
  if (tolower(s[left]) != tolower(s[right])) {
            return false;
        }

   left++;
        right--;
    }

  return true;
    }
}; 
'''

//REVERSE STRING
class Solution {
public:
    void reverseString(vector<char>& s) {
        int start=0,end=s.size()-1;
        while(start<end){
            swap(s[start],s[end]);
            start++;
            end--;
        }
        
  }
};

// LONGEST COMMON PREFIX
class Solution {
public:
    string longestCommonPrefix(vector<string>& s) {
        sort(s.begin(),s.end());
        string s1=s[0],s2=s[s.size()-1];
        int i=0,j=0;
        int count=0;
        while(i<s1.size()&&j<s2.size()){
            if(s1[i]==s2[j]){
                count++;
                i++;
                j++;
            }
            else{
                break;
            }
        }
        return s1.substr(0,count);
    }
};  

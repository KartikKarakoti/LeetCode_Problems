class Solution {
public:
    int removeDuplicates(vector<int>& nums) {

        int index = 1;
        int occurance = 1;

        for(int i=1; i < nums.size(); i++){
            if (nums[i] == nums[i-1]){
                occurance++;
            }else{
                occurance = 1;
            }

            if(occurance <= 2){
                nums[index] = nums[i];
                index++;
            }
        }

        return index;
        
    }
};

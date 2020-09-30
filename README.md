# Find-Pair-with-given-difference-k-
class Solution {
    public int findPairs(int[] nums, int k) {
        if(k<0){
            return 0;
        }
        Arrays.sort(nums);
        int i=0;
        int j =1;
        int count=0;
        while(i<nums.length && j< nums.length){
           if(i!= j && nums[j] - nums[i]== k){
               count++;
               while(j < nums.length && nums[j]-nums[i]==k) j++;// to remove duplicate elements.
           }
            else if(nums[j]-nums[i]<k){
                j++;
            }
            else{
                i++;
            }
        }
        return count;
    }
}

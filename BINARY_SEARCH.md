# ALGORITHMS

// O(logn)

int binarySearch(vector<int>& nums, int target){
  if(nums.size() == 0)
    return -1;

  int start = 0, end = nums.size() - 1;
  while(start <= end){
    // Prevent (left + right) overflow
    int mid = start + (end - start) / 2;
    if(nums[mid] == target){ return mid; }
    else if(nums[mid] < target) { start = mid + 1; }
    else { end = mid - 1; }
  }

 
  return -1;
}

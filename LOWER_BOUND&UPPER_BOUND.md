# ALGORITHMS

#include <bits/stdc++.h>
using namespace std;

int lower_bound(vector<int>& nums, int target)
{
    int low = 0;
    int high = nums.size() - 1;
    int mid;

    while(high - low > 1)
    {
        int mid = (low + high) / 2;
        if(nums[mid] < target)
        {
            low = mid + 1;
        }else{
            high = mid;
        }

    }

    if(nums[low] >= target){ return low; }
    if(nums[high] >= target){ return high; }

    return -1;
}

int upper_bound(vector<int>& nums, int target)
{
    int low = 0;
    int high = nums.size() - 1;
    int mid;

    while(high - low > 1)
    {
        int mid = (low + high) / 2;
        if(nums[mid] <= target)
        {
            low = mid + 1;
        }else{
            high = mid;
        }

    }

    if(nums[low] > target){ return low; }
    if(nums[high] > target){ return high; }

    return -1;
}

int main()
{
    int n;
    cin >> n;

    vector<int> nums;

    for(int i = 0; i < n; ++i)
    {
        int k;
        cin >> k;
        nums.push_back(k);
    }

    int z;
    cin >> z;

    int  lb,ub;
    // cout << "main" << endl;
    lb = lower_bound(nums, z);
    ub = upper_bound(nums, z);
    // cout << "coilling" << endl;

    cout << "Lower bound : "<< lb << endl;
    cout << "Upper bound : " << ub << endl;

    return 0;
}

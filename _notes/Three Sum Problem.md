## Problem
Given an integer array nums, return all the triplets `[nums[i], nums[j], nums[k]]` such that `i != j`, `i != k`, and `j != k`, and `nums[i] + nums[j] + nums[k] == 0`.

Notice that the solution set must not contain duplicate triplets.

**Example 1:**
**Input:** `nums = [-1,0,1,2,-1,-4]
**Output:** `([-1,-1,2],[-1,0,1])`
**Explanation:** 
`nums[0] + nums[1] + nums[2] = (-1) + 0 + 1 = 0.`
`nums[1] + nums[2] + nums[4] = 0 + 1 + (-1) = 0.`
`nums[0] + nums[3] + nums[4] = (-1) + 2 + (-1) = 0.`
The distinct triplets are `[-1,0,1]` and `[-1,-1,2].`
Notice that the order of the output and the order of the triplets does not matter.

## Solution
The solution to this problem incorporates the solution to the [[Two Sum Problem]], as well as the [[Two Pointer Technique]]. After sorting the array, we iterate through the numbers from smallest to largest, choosing each as a "target." With a target chosen, a pointer at the start and end of the remaining array are adjusted until the values sum to said target. The valid sets of three numbers are stored in a [[Java HashSet]]. 

```java
	public  List<List<Integer>> threeSum(int[] nums) {
        Set<List<Integer>> result  = new HashSet<>();
        if(nums.length==0) return new ArrayList<>(result);
        Arrays.sort(nums);
        for(int i=0; i<nums.length-2;i++){ // -2 because min 3 values
	        int j =i+1;
	        int  k = nums.length-1;
            while(j<k){
                int sum = nums[i]+nums[j]+nums[k];
				if(sum==0) result.add(Arrays.asList(nums[i], 
				nums[j++],nums[k--]));
                else if (sum >0) k--;
                else if (sum<0) j++;
            }

        }
        return new ArrayList<>(result);
    }
```
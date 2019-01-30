# Problems and Solutions

> A list of word's and their definitions that you will hear throughout your programming career.

## Two Sums  

```ruby
# Question Ruby
Given an array of integers, return indices of the two numbers such that they add up to a specific target.
You may assume that each input would have exactly one solution, and you may not use the same element twice.

Example:

Given nums = [2, 7, 11, 15], target = 9,

Because nums[0] + nums[1] = 2 + 7 = 9,
return [0, 1].
```

```cpp
// C++
#include <unordered_map>
#include <iostream> 
#include <vector>

using std::unordered_map;
using std::vector;

class Solution 
{
public:
    vector<int> twoSum(vector<int>& nums, int target) 
    {
        unordered_map<int,int> hash;
        auto end= hash.end();
        vector<int> solution(2,0);
        
        for (int i=0;i<nums.size();i++)
        {
            auto find =hash.find(target-nums[i]);
            if(find==end)
            {   
                 hash.emplace(nums[i],i);   
            }
            else
            {
                solution={find->second,i};
                return solution;     
            }     
        }   
    }
};
```

```javascript
# Javascript
const twoSum = (nums, target) => {
    const map = {};
    for (let i = 0; i < nums.length; i++) {
        const val = target - nums[i];
        if (map[val] !== undefined) {
            return [map[val], i];
        }
        map[nums[i]] = i;
    }
};
```

```python
# Python
class Solution(object):
    def twoSum(self, nums, target):
        a ={}
        for i, num in enumerate(nums):
            if target-num in a:
                return [a[target - num], i]
            else:
                a[num] = i
```


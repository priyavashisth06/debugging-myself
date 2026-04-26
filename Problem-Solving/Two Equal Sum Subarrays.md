# __Two Equal Sum Subarrays__

##### Difficulty: Easy    Accuracy: 54.45%    Submissions: 45K+    Points: 2    Average Time: 15m

---

Given an array of integers arr[], return true if it is possible to split it in two subarrays (without reordering the elements), such that the sum of the two subarrays are equal. If it is not possible then return false.

Example 1: <br>
Input: arr[] = [1, 2, 3, 4, 5, 5] <br>
Output: true <br>
Explanation: We can divide the array into [1, 2, 3, 4] and [5, 5]. The sum of both the subarrays are 10.

Example 2: <br>
Input: arr[] = [4, 3, 2, 1] <br>
Output: false <br>
Explanation: We cannot divide the array into two subarrays with equal sum.

--- 

Constraints:
- 1 ≤ arr.size() ≤ 105 
- 1 ≤ arr[i] ≤ 106

---

Expected Complexities:
- Time Complexity: O(n)
- Auxiliary Space: O(1)



## Explanation

Given: 
1. Ek integers ki Array given hai.
2. Return True karna hai agar ham us given array ko do same subarray me split kar dein.
3. In a way ki unka total sum equal ho. 

Example :
```

Given arr = [1, 3, 2, 5, 1]

then, subarray' = [1, 2, 3] and [5, 1]

as for subarray [1, 2, 3] => 1 + 2 + 3 = 6 
also for subarray [5, 1] => 5 + 1 = 6 

(## Note: Order change nahi karna)

```

## __Code Solution :__ 

```python 
class Solution:
    def canSplit(self, arr):
        total = sum(arr)
        
        # If total sum is odd, cannot split equally
        if total % 2 != 0:
            return False
        
        target = total // 2
        curr_sum = 0
        
        # Check if any prefix sum becomes equal to half
        for num in arr:
            curr_sum += num
            if curr_sum == target:
                return True
        
        return False
```

## Code Explaination :

```markdown
#class define kar di 

class Solution: 

#ek function declare kiya 'canSplit' 

    def canSplit(self, arr): 

#ab ek variable bnaya total naam se jisme hum us array ka total sum store karenge

        total = sum(arr)

#ab agar total sum odd hai to false return kar denge
#ab question aata hai, kyu?
#see, agar maan lo total sum 43 hai 
#to usko hum equal halves me split nahi kar payengen in the form of an integer (as it would be 43/2 = 21.5)


    #If total sum is odd, cannot split equally

        if total % 2 != 0:
            return False

#ab ham ek variable declare kar rhe hai target naam se
#jisme total sum ka half store kar rhe hein 

        target = total // 2

#current sum sum for initalize kar diya hia zero se

        curr_sum = 0

#ab ek for loop lga rhe hai us array me
#jo hmare current sum me ek-ek karke har index se value append karga 
#until vo uske half ke equal na ho jaye (i.e. target)
#because agar uska sum half ke equal hai to usko hum, 2 subarray' me easily split kar payenge
#or usko 'True' return kar denge

        # Check if any prefix sum becomes equal to half

        for num in arr:
            curr_sum += num
            if curr_sum == target:
                return True     
        return False

#finally False return kar denge if it is not possible
```

# LEETCODE-Arrays-3151
---

### **Code Explanation**

The method checks whether an array is "special," meaning the parity (even or odd nature) of adjacent elements alternates. Here's how it works:
1. Loop through the array up to the second-to-last element.
2. Check if two consecutive elements have the same parity using the condition:
   ```java
   (nums[i+1] & 1) == (nums[i] & 1)
   ```
   - `nums[i] & 1` checks the last bit of the number, which is `1` for odd numbers and `0` for even numbers.
3. If any two consecutive elements have the same parity, return `false`.
4. If the loop completes without returning `false`, return `true`.

---

### **Dry Run**

Let's take an example and dry run it:

#### Input: `nums = [1, 2, 3, 4]`

1. **Initialization:**
   - `n = nums.length = 4`

2. **Iteration:**
   - **i = 0:**
     - Check `(nums[i+1] & 1) == (nums[i] & 1)`:
       - `nums[1] = 2`, `nums[0] = 1`
       - `(2 & 1) == (1 & 1)` → `0 == 1` → **false**.
     - Parity alternates. Continue.
   - **i = 1:**
     - Check `(nums[i+1] & 1) == (nums[i] & 1)`:
       - `nums[2] = 3`, `nums[1] = 2`
       - `(3 & 1) == (2 & 1)` → `1 == 0` → **false**.
     - Parity alternates. Continue.
   - **i = 2:**
     - Check `(nums[i+1] & 1) == (nums[i] & 1)`:
       - `nums[3] = 4`, `nums[2] = 3`
       - `(4 & 1) == (3 & 1)` → `0 == 1` → **false**.
     - Parity alternates. Continue.

3. Loop completes. Return `true`.

**Output: `true`**

---

#### Input: `nums = [1, 3, 2, 4]`

1. **Initialization:**
   - `n = nums.length = 4`

2. **Iteration:**
   - **i = 0:**
     - Check `(nums[i+1] & 1) == (nums[i] & 1)`:
       - `nums[1] = 3`, `nums[0] = 1`
       - `(3 & 1) == (1 & 1)` → `1 == 1` → **true**.
     - Return `false`.

**Output: `false`**

---

#### Input: `nums = [2, 3, 4, 5]`

1. **Initialization:**
   - `n = nums.length = 4`

2. **Iteration:**
   - **i = 0:**
     - Check `(nums[i+1] & 1) == (nums[i] & 1)`:
       - `nums[1] = 3`, `nums[0] = 2`
       - `(3 & 1) == (2 & 1)` → `1 == 0` → **false**.
     - Parity alternates. Continue.
   - **i = 1:**
     - Check `(nums[i+1] & 1) == (nums[i] & 1)`:
       - `nums[2] = 4`, `nums[1] = 3`
       - `(4 & 1) == (3 & 1)` → `0 == 1` → **false**.
     - Parity alternates. Continue.
   - **i = 2:**
     - Check `(nums[i+1] & 1) == (nums[i] & 1)`:
       - `nums[3] = 5`, `nums[2] = 4`
       - `(5 & 1) == (4 & 1)` → `1 == 0` → **false**.
     - Parity alternates. Continue.

3. Loop completes. Return `true`.

**Output: `true`**

---

### **Conclusion**
- If the parity alternates throughout the array, the method returns `true`.
- If any two consecutive elements have the same parity, the method returns `false`.

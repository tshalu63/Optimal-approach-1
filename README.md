# Algorithm Revision Notes 🚀

A concise guide to foundational array and searching algorithms, comparing Brute Force vs. Optimized approaches.

---

## 1. Kadane’s Algorithm (Maximum Subarray Sum)
*Find the contiguous subarray with the largest sum.*

*   **Brute Force:** Use nested loops to calculate the sum of every possible subarray $(i, j)$.
    *   **TC:** $O(N^2)$ | **SC:** $O(1)$
*   **Optimized (Dynamic Programming):** Iterate once. If the current running sum becomes negative, discard it and reset to 0 (start a new subarray).
    *   **The Logic:** `currentSum = max(element, currentSum + element)`
    *   **TC:** $O(N)$ | **SC:** $O(1)$

---

## 2. Majority Element (Boyer-Moore Voting)
*Find the element that appears more than ⌊n/2⌋ times.*

*   **Brute Force:** Count the frequency of each element using a Hash Map.
    *   **TC:** $O(N)$ | **SC:** $O(N)$
*   **Optimized (Voting Algorithm):** Maintain a `candidate` and a `count`. If `count == 0`, pick the current element as the candidate. If the next element matches, `count++`, else `count--`.
    *   **The Logic:** The majority element "outvotes" all others.
    *   **TC:** $O(N)$ | **SC:** $O(1)$

---

## 3. Product of Array Except Self
*Calculate products for each index without using the division operator.*

*   **Brute Force:** For every index $i$, run a loop to multiply all elements except $nums[i]$.
    *   **TC:** $O(N^2)$ | **SC:** $O(1)$
*   **Optimized (Prefix & Suffix):** Calculate prefix products in the result array first. then, traverse backward to multiply by suffix products using a single variable.
    *   **The Logic:** `Result[i] = (Product of all left) * (Product of all right)`
    *   **TC:** $O(N)$ | **SC:** $O(1)$ (ignoring output array)

---

## 4. Binary Search
*Find a target in a **sorted** array.*

*   **Brute Force (Linear Search):** Check every element one by one from index $0$.
    *   **TC:** $O(N)$ | **SC:** $O(1)$
*   **Optimized (Divide & Conquer):** Compare the target with the middle element. If not found, discard the half where the target cannot exist.
    *   **The Logic:** `mid = low + (high - low) / 2`. Keep cutting the search space in half.
    *   **TC:** $O(\log N)$ | **SC:** $O(1)$

---

## Summary Table


| Algorithm | Brute Force (TC) | Optimized (TC) | Space (Optimized) |
| :--- | :--- | :--- | :--- |
| **Kadane's** | $O(N^2)$ | $O(N)$ | $O(1)$ |
| **Majority Element** | $O(N)$ | $O(N)$ | $O(1)$ |
| **Product Except Self** | $O(N^2)$ | $O(N)$ | $O(1)$ |
| **Binary Search** | $O(N)$ | $O(\log N)$ | $O(1)$ |

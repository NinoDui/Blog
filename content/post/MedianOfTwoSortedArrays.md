---
title: "LeetCode - Median Of Two Sorted Arrays"
tag:
- leetcode
- algorithm
- array
date: 2018-10-02T16:05:19+08:00
draft: true
---

# Hello World!

```java
class Solution {
    public double findMedianSortedArrays(int[] nums1, int[] nums2) {
        int M = nums1.length, N = nums2.length;
        if (M > N) {
            return findMedianSortedArrays(nums2, nums1);
        }
        int halfNums = (M + N + 1) / 2;
        int l = 0, r = M, m1 = 0, m2 = 0;
        while (l <= r) {
            m1 = l + ((r - l) >> 1);
            m2 = halfNums - m1;

            int maxLeftX = (m1 == 0) ? Integer.MIN_VALUE : nums1[m1 - 1];
            int minRightX = (m1 == M) ? Integer.MAX_VALUE : nums1[m1];
            int maxLeftY = (m2 == 0) ? Integer.MIN_VALUE : nums2[m2 - 1];
            int minRightY = (m2 == N) ? Integer.MAX_VALUE : nums2[m2];

            if (maxLeftX <= minRightY && maxLeftY <= minRightX) {
                if ((M + N) % 2 == 1) {
                    return Math.max(maxLeftX, maxLeftY);
                } else {
                    return ((double) Math.max(maxLeftX, maxLeftY) + Math.min(minRightX, minRightY)) / 2;
                }
            } else if (maxLeftX > minRightY) {
                r = m1 - 1;
            } else {
                l = m1 + 1;
            }
        }
        return 0;
    }
}
```


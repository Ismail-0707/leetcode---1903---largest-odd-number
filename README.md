# Largest Odd Number in String

## Problem Statement

Given a string `num` representing a large integer, return the largest-valued odd integer (as a string) that is a non-empty substring of `num`. If no odd integer exists, return an empty string `""`.

## Approach

An integer is odd if its last digit is odd (`1, 3, 5, 7, 9`).

1. Traverse the string from right to left.
2. Find the first odd digit.
3. Return the substring from index `0` to that digit.
4. If no odd digit is found, return an empty string.

## Java Solution

```java
class Solution {
    public String largestOddNumber(String num) {
        for (int i = num.length() - 1; i >= 0; i--) {
            int digit = num.charAt(i) - '0';

            if (digit % 2 != 0) {
                return num.substring(0, i + 1);
            }
        }

        return "";
    }
}

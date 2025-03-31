---
tags:
  - published
---
Problem: Given an input string, remove all instances of the `$` characters in [[O(n)]] time. 

## Naive Solution

Iterate through input string. When a quote character is found, remove it and shift all characters to the left by one. In the worst case scenario where every character in the string is `$` this number of operations is consistent with an [[Arithmetic Series]] and thus runs in [[O(n-squared)]]. For example, if the string was `$$$$$`, the number of operations would be 5 operations for processing the first character, 4 for next, then 3, and so on.

## O(n) Solution

Copy all non-quote characters to a destination storage and return. $O(n)$. This can be done [[In-Place]], without requiring external storage: simply maintain one pointer to move along the string and parse each character, and another pointer that lags behind, inputting each parsed character that isn’t `$`. 

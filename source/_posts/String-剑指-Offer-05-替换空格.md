---
title: String-剑指 Offer 05. 替换空格
date: 2023-08-11 17:23:39
tags:
- two pointers
---
```
class Solution:
    def replaceSpace(self, s: str) -> str:
        counter=s.count(' ')
        res=list(s)
        res.extend([' ']*counter*2)
        left,right=len(s)-1,len(res)-1
        while left>=0:
            if res[left] !=' ':
                res[right]=res[left]
                right-=1
            else:
                res[right-1:right+1]='%20'
                right-=3
            left-=1
        return ''.join(res)

```

Certainly! Let's break down each line of the given code step by step and explain its purpose:

```
class Solution:
    def replaceSpace(self, s: str) -> str:
        counter = s.count(' ')
```
class Solution:: Defining a class named Solution.
def replaceSpace(self, s: str) -> str:: Defining a method named replaceSpace that takes a string s as an argument and returns a string.
counter = s.count(' '): Counting the number of space characters (' ') in the input string s and storing the count in the variable counter.
```
        res = list(s)
```
res = list(s): Creating a list named res by converting the input string s into a list of characters. This list will be used to perform the replacement.
```
        res.extend([' '] * counter * 2)
```
res.extend([' '] * counter * 2): Extending the res list by appending a list of space characters ' ' repeated counter * 2 times. This is done to allocate enough space for the replacement strings %20.
```
        left, right = len(s) - 1, len(res) - 1
```
left, right = len(s) - 1, len(res) - 1: Initializing two pointers, left and right, to the indices representing the current character positions in the original string s and the extended list res, respectively.
```
        while left >= 0:
```
while left >= 0:: Starting a while loop that continues as long as the left pointer is greater than or equal to 0, which means there are more characters to process.
```
            if res[left] != ' ':
                res[right] = res[left]
                right -= 1
            else:
                res[right - 2: right + 1] = '%20'
                right -= 3
            left -= 1
```
Inside the loop, the code checks whether the character at the left position is not a space. If it's not a space, the character is copied to the right position, and both pointers are moved to the left. If it is a space, the %20 replacement is written to the right position, and both pointers are moved accordingly.
```
        return ''.join(res)
```
After the loop, the code joins the modified list res back into a string using the join() method and returns the result.
This code replaces spaces in the input string s with %20, while also efficiently managing the additional space required for the replacements.




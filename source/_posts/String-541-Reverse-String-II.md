---
title: String|541. Reverse String II
date: 2023-08-11 16:07:46
tags:
- string
---
- Solution 1
```
class Solution:
    def reverseStr(self,s: str, k: int) -> str:
        result=[]
        length=len(s)
        for i in range(0,length//(k)+1):
            reversed_chunk=s[2*i*k:(2*i+1)*k][::-1]
            result.append(reversed_chunk+s[(2*i+1)*k:(2*i+2)*k])  
        return ''.join(result) 
```
* range(0,0)返回的是none，我在做题的时候使用了for i in range(0,length//(k))，该范围略过了当length小于k的情况
- Solution 2
```
def reverseStr(self, s: str, k: int) -> str:
        length = len(s)
        result = []  # Use a list to accumulate the result
        for i in range(0,length,2*k): # the increament of i is 2k
            chuck=s[i:i+k] #Getthe first k characters
            reversed_chunck=chuck[::-1]
            #append the result of reversed chuck and the rest of the characters
            result.append(reversed_chuck + s[i+k:i+2*k])
        return ''.join(result)

```
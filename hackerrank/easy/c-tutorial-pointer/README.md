# Functions

![Difficulty](https://img.shields.io/badge/Difficulty-Easy-green)

## Problem

A [pointer](http://en.wikipedia.org/wiki/Pointer_%28computer_programming%29) in C++ is used to share a memory address among different contexts (primarily functions). They are used whenever a function needs to modify the content of a variable, but it does not have ownership.  
<br>
In order to access the memory address of a variable, $val$, prepend it with $\&$ sign. For example, `&val` returns the memory address of $val$.  
<br>
This memory address is assigned to a pointer and can be shared among functions. For example, $int^* p = \&val$ assigns the memory address of $val$ to pointer $p$. To access the content of the memory pointed to, prepend the variable name with a `*`. For example, `*p` will return the value stored in $val$ and any modification to it will be performed on $val$.

	void increment(int *v) {
    	(*v)++;
    }
    
    int main() {
    	int a;
        scanf("%d", &a);
        increment(&a);
        printf("%d", a);
    	return 0;
    }  
    
**Function Description**  

Complete the *update* function in the editor below.  

*update* has the following parameters:  

- *int \*a:* an integer  
- *int \*b:* an integer  

**Returns**  

- The function is declared with a `void` return type, so there is no value to return. Modify the values in memory so that $a$ contains their sum and $b$ contains their absoluted difference.  

- $a' = a+b$
- $b' = |a-b|$

**Input Format**

Input will contain two integers, $a$ and $b$, separated by a newline.

**Constraints**

 

**Output Format**

## Solution

**Language:** C++  
**Runtime:** N/A  
**Memory:** N/A  
**Submitted:** 2026-09-11T15:36:43.639Z  

```cpp
#include <iostream>
#include <cstdio>
#include <vector>
#include <algorithm>
using namespace std;

/*
Add `int max_of_four(int a, int b, int c, int d)` here.
*/
int max_of_four(int a,int b,int c,int d){
     vector<int>vec;
     vec.push_back(a);
     vec.push_back(b);
     vec.push_back(c);
     vec.push_back(d);
     std::sort(vec.begin(),vec.end(),std::greater<int>());
     return (vec[0]);
     
}

int main() {
    int a, b, c, d;
    scanf("%d %d %d %d", &a, &b, &c, &d);
    int ans = max_of_four(a, b, c, d);
    printf("%d", ans);
    
    return 0;
}

```

---

[View on HackerRank](https://www.hackerrank.com/challenges/c-tutorial-pointer/problem)
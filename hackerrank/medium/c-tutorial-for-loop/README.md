# Conditional Statements

![Difficulty](https://img.shields.io/badge/Difficulty-Medium-yellow)

## Problem

A _for_ loop is a programming language statement which allows code to be repeatedly executed.  

The syntax is

	for ( <expression_1> ; <expression_2> ; <expression_3> )
    	<statement>

- _expression\_1_ is used for intializing variables which are generally used for controlling the terminating flag for the loop.
- _expression\_2_ is used to check for the terminating condition. If this evaluates to false, then the loop is terminated.
- _expression\_3_ is generally used to update the flags/variables.

A sample loop is

	for(int i = 0; i < 10; i++) {
    	...
    }
    
In this challenge, you will use a for loop to increment a variable through a range.  

**Input Format**

You will be given two positive integers, $a$ and $b$ ($a \le b$), separated by a newline.

**Constraints**

 

**Output Format**

For each integer $n$ in the inclusive interval $[a, b]$:

- If $1 \le n \le 9$, then print the English representation of it in lowercase. That is "one" for $1$, "two" for $2$, and so on.
- Else if $n > 9$ and it is an even number, then print "even".
- Else if $n > 9$ and it is an odd number, then print "odd".

**Note:** $[a, b] = \{x \in \mathbb{Z} \,|\, ~a \le x \le b\} = \{a, ~a+1, \dots, b\}$

## Solution

**Language:** C++  
**Runtime:** N/A  
**Memory:** N/A  
**Submitted:** 2026-08-28T15:00:45.066Z  

```cpp
#include <bits/stdc++.h>
#include <string>
#include <vector>
#include <algorithm>


using namespace std;

string ltrim(const string &);
string rtrim(const string &);



int main()
{
    string n_temp;
    getline(cin, n_temp);

    int n = stoi(ltrim(rtrim(n_temp)));
    string represent[]={"zero","one","two","three","four","five","six","seven","eight","nine"};
    // Write your code here
    if(n<=9 && n>=1){
        
        cout<<represent[n]<<endl;
    } else{
        cout<<"Greater than 9"<<endl;
    }

    return 0;
}

string ltrim(const string &str) {
    string s(str);

    s.erase(
        s.begin(),
        find_if(s.begin(), s.end(), not1(ptr_fun<int, int>(isspace)))
    );

    return s;
}

string rtrim(const string &str) {
    string s(str);

    s.erase(
        find_if(s.rbegin(), s.rend(), not1(ptr_fun<int, int>(isspace))).base(),
        s.end()
    );

    return s;
}

```

---

[View on HackerRank](https://www.hackerrank.com/challenges/c-tutorial-for-loop/problem)
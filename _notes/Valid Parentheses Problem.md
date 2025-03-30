---
tags:
  - published
---
## Problem 

Given a string `s` containing just the characters `'('`, `')'`, `'{'`, `'}'`, `'['` and `']'`, determine if the input string is valid.

An input string is valid if:

1. Open brackets must be closed by the same type of brackets.
2. Open brackets must be closed in the correct order.
3. Every close bracket has a corresponding open bracket of the same type.

## Solution

The following basic solution solves the problem by keeping counters for each parentheses pair, incrementing the counter when an opening bracket is encountered, and decrementing the counter when a closing bracket is found:

```js
if (a ==b){
  test;
}
```


```C
bool isValid(char* s) {
    int parensFound = 0;
    int curliesFound = 0;
    int squaresFound = 0;

    for (int i = 0; i < strlen(s); i++){
        if (s[i] == '('){
            parensFound++;
        }
        if (s[i] == '{'){
            curliesFound++;
        }
        if (s[i] == '['){
            squaresFound++;
        }

        if (s[i] == ')'){
            parensFound--;
        }
        if (s[i] == '}'){
            curliesFound--;
        }
        if (s[i] == ']'){
            squaresFound--;
        }
    }

    return (parensFound == 0 && curliesFound == 0 && squaresFound == 0);
}
```
# Valid Parentheses

---

Given a string containing just the characters`'('`,`')'`,`'{'`,`'}'`,`'['`and`']'`, determine if the input string is valid.

An input string is valid if:

1. Open brackets must be closed by the same type of brackets.
2. Open brackets must be closed in the correct order.

Note that an empty string is also considered valid.

---

```
class Solution(object):
    def isValid(self, s):
        """
        :type s: str
        :rtype: bool
        """
        stack = []
        
        mapping = {")": "(", "}": "{", "]": "["}
        
        for ch in s:
            if ch in mapping:
                top = stack.pop() if stack else '#'
                if top != mapping[ch]:
                    return False
            else:
                stack.append(ch)
        
        return not stack
```

---

### Key Learning Points

1. Use dictionary for smart mapping of parentheses
2. NOT Array will return true if  Array is empty




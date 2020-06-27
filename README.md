# Generate Parentheses
## https://leetcode.com/problems/generate-parentheses

Given n pairs of parentheses, write a function to generate all combinations of well-formed parentheses.

For example, given n = 3, a solution set is:

[
  "((()))",
  "(()())",
  "(())()",
  "()(())",
  "()()()"
]

## Implementation :
```java
class Solution {
    public List<String> generateParenthesis(int n) {
        List<String> list = new ArrayList<>();
        helper(list, "" , 0, 0, n);
        return list;
    }
    
    private void helper(List<String> list , String current, int open, int closed, int n) {
        if(current.length() == n * 2) {
            list.add(current);
            return;
        }
        
        if(open < n) {
            helper(list, current + "(", open + 1, closed, n);
        }
        
        if(closed < open) {
            helper(list, current + ")", open, closed + 1, n);
        }
            
    }
}
```

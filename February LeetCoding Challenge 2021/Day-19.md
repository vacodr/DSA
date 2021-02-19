# Minimum Remove to Make Valid Parentheses
Given a string s of '(' , ')' and lowercase English characters. 

Your task is to remove the minimum number of parentheses ( '(' or ')', in any positions ) so that the resulting parentheses string is valid and return any valid string.

Formally, a parentheses string is valid if and only if:

It is the empty string, contains only lowercase characters, or
It can be written as AB (A concatenated with B), where A and B are valid strings, or
It can be written as (A), where A is a valid string.

Problem type: Medium

Link: https://leetcode.com/problems/minimum-remove-to-make-valid-parentheses/
## Code
```java
class Solution {

    public String minRemoveToMakeValid(String s) {
        Stack<Pair<Character, Integer>> st = new Stack<>();
        for(int i=0;i<s.length();i++){
            char c = s.charAt(i);
            if(c == ')' || c == '('){
                if(st.empty()){
                    st.push(new Pair<>(c, i));
                } else{
                    if(c == ')' && st.peek().getKey() == '('){
                        st.pop();
                    } else{
                        st.push(new Pair<>(c, i));
                    }
                }
            }
        }

        Set<Integer> indexesToBeRemoved = new HashSet<>();
        while(!st.empty()){
            indexesToBeRemoved.add(st.peek().getValue());
            st.pop();
        }

        String ans = "";
        for(int i=0;i<s.length();i++){
            if(!indexesToBeRemoved.contains(i)){
                ans += s.charAt(i);
            }
        }

        return ans;
    }
}
```

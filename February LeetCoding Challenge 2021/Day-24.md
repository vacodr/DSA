# Score of Parentheses
Given a balanced parentheses string S, compute the score of the string based on the following rule:

* () has score 1
* AB has score A + B, where A and B are balanced parentheses strings.
* (A) has score 2 * A, where A is a balanced parentheses string.

Problem type: Medium

Link: https://leetcode.com/problems/score-of-parentheses/
## Code
```java
class Solution {
  
    public int scoreOfParentheses(String s) {
        Stack<String> st = new Stack<>();

        for(int i =0; i<s.length();i++){
            char c = s.charAt(i);
            if(st.empty()){
                st.push(c + "");
            } else {
                if(c == ')'){
                    int innerScore = 0;
                    while(!st.empty() && !st.peek().equals("(")){
                        innerScore += Integer.valueOf(st.peek());
                        st.pop();
                    }
                    st.pop();

                    if(innerScore == 0){ 
                        st.push("1");
                    } else{
                        st.push(2*innerScore + "");
                    }
                } else{
                    st.push(c + "");
                }
            }
        }

        int score = 0;
        while(!st.empty()){ 
            score += Integer.valueOf(st.peek());
            st.pop();
        }
        return score;
    }
}
```

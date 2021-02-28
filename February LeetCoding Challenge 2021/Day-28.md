# Maximum Frequency Stack
Implement FreqStack, a class which simulates the operation of a stack-like data structure.

FreqStack has two functions:

* push(int x), which pushes an integer x onto the stack.
* pop(), which removes and returns the most frequent element in the stack.
* If there is a tie for most frequent element, the element closest to the top of the stack is removed and returned.

Problem type: Hard

Link: https://leetcode.com/problems/maximum-frequency-stack/
## Code
```java
class FreqStack {

    List<Stack<Integer>> stList = null;
    Map<Integer, Integer> map = null;

    public FreqStack() {
        map = new HashMap<>();
        stList = new ArrayList<>();

    }

    public void push(int x) {
        map.put(x, map.getOrDefault(x, 0)+1);
        int freq = map.get(x);
        if(freq -1 >= stList.size()){
            stList.add(new Stack<Integer>());
        }
        stList.get(freq-1).add(x);

    }

    public int pop() {
        int size = stList.size();
        int x = stList.get(size-1).pop();
        if(stList.get(size-1).empty()){
            stList.remove(size-1);
        }

        map.put(x, map.get(x)-1);
        if(map.get(x) == 0){
            map.remove(x);
        }

        return x;

    }
}
```

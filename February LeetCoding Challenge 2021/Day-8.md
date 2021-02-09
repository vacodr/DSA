# 284. Peeking Iterator
Given an Iterator class interface with methods: next() and hasNext(), design and implement a PeekingIterator that support the peek() operation -- it essentially peek() at the element that will be returned by the next call to next().

Problem type: Medium

Link: https://leetcode.com/problems/peeking-iterator/
## Code
```java
class PeekingIterator implements Iterator<Integer> {
    // Peek element
    Integer nextEl = null;
    Iterator<Integer> it = null;
    public PeekingIterator(Iterator<Integer> iterator) {
        // initialize any member here.
        this.it = iterator;
        nextEl = it.next();
    }

    // Returns the next element in the iteration without advancing the iterator.
    public Integer peek() {
        return nextEl;
    }

    // hasNext() and next() should behave the same as in the Iterator interface.
    // Override them if needed.
    @Override
    public Integer next() {
        Integer valueToReturn = nextEl;
        if(it.hasNext()){
            this.nextEl = it.next();
        } else{
            this.nextEl = null;
        }
        return valueToReturn;
    }

    @Override
    public boolean hasNext() {
        return nextEl!=null;
    }
}
```

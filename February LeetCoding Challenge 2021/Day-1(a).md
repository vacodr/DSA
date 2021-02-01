# Number of 1 Bits
Write a function that takes an unsigned integer and returns the number of '1' bits it has (also known as the Hamming weight).

Problem type : Easy
## Code
```java

public int hammingWeight(int n) {
    int m = 0;
    int bit = 1;
    for (int i = 0; i < 32; i++) {
        if ((n & bit) != 0) {
            m++;
        }
        bit <<= 1;
    }
    return m;
}

```

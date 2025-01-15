# Leetcode---2429
Minimize XOR
//CODE IN JAVA
public class Solution {
    public int minimizeXor(int num1, int num2) {
        int count = Integer.bitCount(num2);
        int result = 0;
        
        for (int i = 31; i >= 0 && count > 0; i--) {
            if ((num1 & (1 << i)) != 0) {
                result |= (1 << i);
                count--;
            }
        }
        
        for (int i = 0; i <= 31 && count > 0; i++) {
            if ((num1 & (1 << i)) == 0) {
                result |= (1 << i);
                count--;
            }
        }
        
        return result;
    }
}


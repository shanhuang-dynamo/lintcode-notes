[013. strStr](http://www.lintcode.com/problem/strstr)

- [prev: 012. Min Stack](012-min-stack.md)
- [next: 014. First Position of Target](014-first-position-of-target.md)

---
###Note:
[substring](http://www.tutorialspoint.com/java/java_string_substring.htm)
###Solution:
```java
class Solution {
    /**
     * Returns a index to the first occurrence of target in source,
     * or -1  if target is not part of source.
     * @param source string to be scanned.
     * @param target string containing the sequence of characters to match.
     */
    public int strStr(String source, String target) {
        if(source == null || target == null || target.length()>source.length()) 
            return -1;
        if(target == "") return 0; //corner case that target is empty
        for(int i=0;i<source.length()-target.length()+1;i++){
            for(int j=0;j<target.length();j++){
                if(target.charAt(j)!=source.charAt(i+j))
                    break;
                else{
                    if(j==target.length()-1) return i;
                    continue;
                }
            }
        }
        return -1;
    }
}
```

---

- [prev: 012. Min Stack](012-min-stack.md)
- [next: 014. First Position of Target](014-first-position-of-target.md)

[013. strStr](http://www.lintcode.com/problem/strstr)

- [prev: 012. Min Stack](012-min-stack.md)
- [next: 014. First Position of Target](014-first-position-of-target.md)

---

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
        for(int i=0;i<source.length()-target.length()+1;i++){
            // substring(beg_ind, end_ind), includes beg_ind, excludes end_ind
            // [substring](http://www.tutorialspoint.com/java/java_string_substring.htm)
            String substr = source.substring(i,i+target.length());
            if(!substr.equals(target))
                continue;
            else
                return i;
        }
        return -1;
    }
}
```

---

- [prev: 012. Min Stack](012-min-stack.md)
- [next: 014. First Position of Target](014-first-position-of-target.md)

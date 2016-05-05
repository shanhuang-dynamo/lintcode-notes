[017. Subsets](http://www.lintcode.com/problem/subsets)

- [prev: 016. Permutations II](016-permutations-ii.md)
- [next: 018. Subsets II](018-subsets-ii.md)

---
###Notes:
- Iterative algorithm for Power set:
<script src='https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML'></script>
$$PS(A\cup \{e\})= PS(A)\cup\{\{e\}\cup B|\forall B\in PS(A)\}$$
- recursive algorithm for Poswer Set:
TODO
###Code:
#### Iterative algorithm for Power set:
```java
class Solution {
    /**
     * @param S: A set of numbers.
     * @return: A list of lists. All valid subsets.
     */
    public ArrayList<ArrayList<Integer>> subsets(int[] nums) {
        //First sort the array nums in descending order (using bubble sort)
        for(int i=0;i<nums.length-1;i++){
            for(int j=0;j<nums.length-1-i;j++){
                if(nums[j]<nums[j+1]){
                    int temp=nums[j];
                    nums[j]=nums[j+1];
                    nums[j+1]=temp;
                }
            }
        }
        ArrayList<ArrayList<Integer>> allSet = new ArrayList<ArrayList<Integer>>();
        allSet.add(new ArrayList<Integer>());
        for (int i = 0; i < nums.length; i++) {
            ArrayList<ArrayList<Integer>> subSet = new ArrayList<ArrayList<Integer>>();
            for (int j = 0; j < allSet.size(); j++) {
                ArrayList<Integer> element = new ArrayList<Integer>();
                element.add(nums[i]);
                element.addAll(allSet.get(j));
                subSet.add(element);
            }
            allSet.addAll(subSet);
        }
        return allSet;
    }
}
```
####recursive algorithm for Poswer Set: TODO

---

- [prev: 016. Permutations II](016-permutations-ii.md)
- [next: 018. Subsets II](018-subsets-ii.md)

[017. Subsets](http://www.lintcode.com/problem/subsets)

- [prev: 016. Permutations II](016-permutations-ii.md)
- [next: 018. Subsets II](018-subsets-ii.md)

---
### Notes:
- Iterative algorithm for Power set:
![iterative algorithm](http://chart.googleapis.com/chart?cht=tx&chl=PS%5C(%5C%7Be%5C%7D%5Ccup%20A%5C)%3D%5C%7B%5C%7Be%5C%7D%5Ccup%20A'%7C%20%5Cforall%20A'%5Cin%20PS(A)%5C%7D%5Ccup%20PS(A))
- recursive algorithm for Poswer Set:
TODO

### Code:
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

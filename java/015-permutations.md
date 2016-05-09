[015. Permutations](http://www.lintcode.com/problem/permutations)

- [prev: 014. First Position of Target](014-first-position-of-target.md)
- [next: 016. Permutations II](016-permutations-ii.md)

---
### Notes
did not pass the corner test of null or [] input

### code

```java
public class Solution {
	/**
     * @param nums: A list of integers.
     * @return: A list of permutations.
     */
	public ArrayList<ArrayList<Integer>> permute(ArrayList<Integer> nums) {
		ArrayList<ArrayList<Integer>> result = new ArrayList<ArrayList<Integer>>();
		//start from an empty list
		result.add(new ArrayList<Integer>());
        int n=nums.size();
        for(int i=0;i<n;i++){
        	ArrayList<ArrayList<Integer>> current = new ArrayList<ArrayList<Integer>>();
        	for (ArrayList<Integer> l: result){
        		//insert nums.get(i) to different locations
        		// #available locations to insert is: l.size()+1
        		for(int j=0;j<l.size()+1;j++){
        			ArrayList<Integer> temp = new ArrayList<>(l);
        			temp.add(j,nums.get(i));
        			current.add(temp);
        		}
        	}
            result = new ArrayList<ArrayList<Integer>>(current);
        }
        return result;
    }
}

```
---

- [prev: 014. First Position of Target](014-first-position-of-target.md)
- [next: 016. Permutations II](016-permutations-ii.md)

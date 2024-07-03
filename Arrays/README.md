# Arrays/Hashing
<ul>
<li>The most ESSENTIAL algorithm/pattern to learn for future concepts presented in this cheat sheet. Remember, if you don't know what to do probably just throw a HashMap at it.</li>
<li> Hashing/Hashmaps are mainly used for counting the frequencies in arrays within the first pass and often creates a space and iteration complexity of O(n) for both, since a look up is usually of O(1) in a hashMap/hashSet or character array.
<li> There are times when only letters are required, i.e. Capitals or Lowercase letters only, such that you need a list of zeros representing the ith letter’s frequency in an array
<li> K-frequent elements actually utilizes a form of hashing/sort called bucket sort in which since we need the k-most frequent elements in a fixed list we can concur that the max amount of frequency that can happen is the length of the list and the minimum is 0.
<ul> <li> For example, [1,1,1,2,3,3] the bucket list would look something like: [[], [2], [3], [1], [], []]
</ul>
</ul>

## hasDuplicate
```python
class Solution:
    def hasDuplicate(self, nums: List[int]) -> bool:
        checker = {}
        for i in nums:
            if i in checker:
                return True
            else:
                checker[i] = 0
        return False
```
**Time Complexity: O(n) Space Complexity O(n)** <br>
We iterate through the entire array and utilize a hashmap to do lookups of O(1) time for each element that we encounter in the array. As such we get a time complexity of O(n) but a space complexity of O(n) due to having to create another data structure for each element in the array.

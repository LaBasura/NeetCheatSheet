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

## twoSum
```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        prevMap = {}  # val -> index

        for i, n in enumerate(nums):
            diff = target - n
            if diff in prevMap:
                return [prevMap[diff], i]
            prevMap[n] = i
```
**Time Complexity: O(n) Space Complexity O(n)** <br>
We iterate through the entire array and utilize a hashmap to do lookups of O(1). The logic is we iterate through the array and look up whether the second number to the sum is present in the array. Since two sum is essentially current + x = target, in order to find x we simply convert it into x = target - current and x is guaranteed to be within the array so we simply store every element of the array in a dictionary to look up later. As such we get a time complexity of O(n) but a space complexity of O(n) due to having to create another data structure for each element in the array.

## groupAnagrams
```python
class Solution:
    def groupAnagrams(self, strs: List[str]) -> List[List[str]]:
        dic = defaultdict(list)
        for i in strs:
            alphabet = [0] * 26
            for c in i:
                alphabet[ord(c)-ord('a')] = alphabet[ord(c)-ord('a')] + 1
            key = tuple(alphabet)
            dic[key].append(i)
        return dic.values()
```
**Time Complexity: O(n) Space Complexity O(n)** <br>
Given a list of strings we want to go from Input: ["act","pots","tops","cat","stop","hat"] -> [["hat"],["act", "cat"],["stop", "pots", "tops"]]. We iterate through every element and count the frequencies of each character utilizing a character frequencies array which creates O(26) lookups, then using that same array as a key into an 'anagram' dictionary of lists as elements and appending the string to it.

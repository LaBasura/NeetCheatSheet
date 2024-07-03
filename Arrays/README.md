# Arrays/Hashing
<ul>
<li> mainly used for counting the frequencies in arrays within the first pass and often creates a space and iteration complexity of O(n) for both, since a look up is usually of O(1) in a hashMap/hashSet or character array.
<li> There are times when only letters are required, i.e. Capitals or Lowercase letters only, such that you need a list of zeros representing the ith letter’s frequency in an array
<li> K-frequent elements actually utilizes a form of hashing/sort called bucket sort in which since we need the k-most frequent elements in a fixed list we can concur that the max amount of frequency that can happen is the length of the list and the minimum is 0.
<ul> <li> For example, [1,1,1,2,3,3] the bucket list would look something like: [[], [2], [3], [1], [], []]
</ul>
</ul>

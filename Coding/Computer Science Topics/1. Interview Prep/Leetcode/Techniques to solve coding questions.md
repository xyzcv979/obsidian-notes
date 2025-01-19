
## 1. Visualize the problem by drawing it out
Drawing diagrams are useful for understanding the internal states

## 2. Think about how you would solve the problem by hand
Solve it like a non-programmer would. Especially useful for trees/graphs, imagining how to get the solution

## 3. Come up with more examples
Helps reinforce your understanding of the question, prevents premature jumping into coding, helps identify the pattern. Lastly, more examples can be used as test cases when verifying the solution

## 4. Break the question down into smaller independent parts
If problem is large, start with high level function and break it down into smaller functions. Keeps your thinking structured, modular. 
Doing so makes it clear to interviewer that you have an approach even if you don't finish coding all the sub functions

Example for group anagrams problem. It is broken down into 2 parts to solve the problem, hashing the string and grouping those hashes together

```python
def group_anagrams(strings):
  def hash(string):
    # Fill in later
    pass

  def group_strings(strings_hashes):
    # Fill in later
    pass

  strings_hashes = [(string, hash(string)) for string in strings]
  return group_strings(strings_hashes)
```

## 5. Apply common data structures and algorithms

### Data structures to keep in mind:
- **Hash maps**: Useful for efficient lookups
- **Stacks and Queue**: Useful for something like parsing a string for nested properties (math equation)
- **Heap**: Question involves scheduling/ordering based on some priority. Also useful for finding max K / min K / median elements in set
- **Tree/Trie**: If you need to store strings in space-efficient manner and look for existence of strings very quickly
- **Graphs**: If data presented to you has associations between entities.
### Algorithms:
- **Sorting**
- **Binary search**: Useful if array is sorted and you need to do faster than `O(N)` searches
- **Sliding window**
- **Two pointers**
- **Union Find**
- **BFS/DFS**
- **Traverse from the back**
- **Topological sorting**



## Optimizing your approach/solution
"Can we optimize further?"

### Optimize time complexity
1. Identify Best Theoretical Time Complexity (**BTTC**) of the solution
	1. Important to know BTTC so you don't go down rabbit hole of finding something better.
		- BTTC of finding sum of array is `O(n)`, you have to look at each num at least once
		- BTTC of finding number of groups of anagrams is` O(nk)` where n = num of words and k is max num of letters in a word. You have to look at each word and letters in the word at least once
		- BTTC of finding num of islands is `O(nm)` where n = num of rows and m = num of columns. You have to search each cell at least once
2. Identify overlapping and repeated computation
	1. Consider if you can reuse results from previous computation. Dynamic programming leverages this. 
3. Try different data structures
	1. Different data structures optimize further
	2. Example, if the lookup is your bottleneck, you can use hash map to optimize the lookup
	3. Example: K closest points to Origin problem
		1. Can solve naively by calculating distance of each point and sorting them and taking K smallest values.` O(nlog(n))` time
		2. Optimize version: Use heap and add/remove only up to k items so time complexity is now `O(log(k))`
4. Identify redundant work
	1. Dont check conditions unnecessarily
	2. mind the order of conditional checks
	3. Don't invoke methods unnecessarily
	4. Early termination: stop after you have an answer and return it
	5. Minimize work inside loops: don't redo work you already have done if it doesn't change
	6. Be lazy: If the input is empty, just return. Don't need to loop it

### Optimize Space complexity
When optimize time complexity is reached, space complexity optimization might be asked

1. Changing data in-place
	1. Overwrite values in original input array but be careful not to destroy input data in irreversible ways if it's used later
2. Change the data structure
	1. Are you using the best data structure possible for the problem?
3. 
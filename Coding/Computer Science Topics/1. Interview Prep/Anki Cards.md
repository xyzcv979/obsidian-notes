
TARGET DECK: Leetcode::Neetcode 75::17. Math & Geometry
START
Basic
54. Spiral Matrix  

Description: Given an m x n matrix, return all elements of the matrix in spiral order.

Example:
`Input: [  [ 1, 2, 3 ],  [ 4, 5, 6 ],  [ 7, 8, 9 ] ] Output: [1,2,3,6,9,8,7,4,5]`
Back: 
```python
class Solution:
    def spiralOrder(self, matrix: List[List[int]]) -> List[int]:
        if not matrix:
            return []
        
        result = []
        top, bottom, left, right = 0, len(matrix) - 1, 0, len(matrix[0]) - 1
        
        while top <= bottom and left <= right:
            # Traverse top row
            for i in range(left, right + 1):
                result.append(matrix[top][i])
            top += 1
            
            # Traverse rightmost column
            for i in range(top, bottom + 1):
                result.append(matrix[i][right])
            right -= 1
            
            # Traverse bottom row
            if top <= bottom:  # to avoid duplicate traversal in case of odd rows
                for i in range(right, left - 1, -1):
                    result.append(matrix[bottom][i])
                bottom -= 1
            
            # Traverse leftmost column
            if left <= right:  # to avoid duplicate traversal in case of odd columns
                for i in range(bottom, top - 1, -1):
                    result.append(matrix[i][left])
                left += 1
        
        return result
```
Complexity Analysis:
- Time complexity: O(m*n), where m is the number of rows and n is the number of columns in the matrix.
- Space complexity: O(1) (excluding the output list).
<!--ID: 1714399824436-->
END
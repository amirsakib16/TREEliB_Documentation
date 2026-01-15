#  Binary Tree Operations Library

A comprehensive Python library for binary tree manipulation, traversal, and analysis. This library provides an extensive set of operations for working with binary trees, from basic creation and traversal to advanced operations like balancing checks, path finding, and tree transformations.

# Read the TREEliB Documentation
<p align="center">
  <img src="https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white" alt="Vercel Badge" />
  <br />
  <a href="https://tre-eli-b-documentation.vercel.app/" target="_blank">
    <img src="https://img.shields.io/badge/HERE-Read_Documentation-brightgreen?style=flat-square" alt="Live Demo" />
  </a>
</p>

## Features

### Core Operations
- **Tree Construction**: Build binary trees from arrays with level-order insertion
- **Multiple Traversals**: In-order, Pre-order, Post-order, and Level-order traversal
- **Tree Analysis**: Height, depth, diameter, width, and density calculations
- **Tree Validation**: Check for BST, AVL, complete, full, perfect, balanced, and symmetric trees
- **Path Operations**: Find paths, calculate path sums, and determine distances between nodes
- **Tree Modifications**: Invert, flip, merge, add/delete nodes, and serialize/deserialize
- **Advanced Features**: Find LCA, check for subtrees, get different views (top, bottom, left, right)

### Supported Operations
- 60+ tree operations
- Efficient algorithms with optimized time complexity
- Comprehensive error handling
- Clean and intuitive API

## Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/binary-tree-library.git

# Navigate to the directory
cd binary-tree-library

# Install dependencies (if any)
pip install -r requirements.txt
```

##  Quick Start

```python
from binary_tree import BinaryTree

# Create a binary tree from an array
tree = BinaryTree()
array = [1, 2, 3, 4, 5, 6, 7]

# Print in different traversal orders
tree.printIN(array)    # In-order: 4 2 5 1 6 3 7
tree.printPRE(array)   # Pre-order: 1 2 4 5 3 6 7
tree.printPOST(array)  # Post-order: 4 5 2 6 7 3 1
tree.printLVL(array)   # Level-order: 1 2 3 4 5 6 7

# Get tree properties
nodes = tree.CountNodes(array)        # Returns: 7
max_depth = tree.MAXdepth(array)      # Returns: 3
is_balanced = tree.checkBalanced(array)  # Returns: True
```

##  API Reference

### Tree Construction

#### `Create(array)`
Constructs a binary tree from a list using level-order insertion.

```python
tree = BinaryTree()
root = tree.Create([1, 2, 3, 4, 5, None, 7])
```

**Parameters:**
- `array` (list): List representation of the binary tree. Use `None` for missing nodes.

**Returns:** Root node of the constructed tree.

---

### Tree Traversal

#### `printIN(array)`
Prints the tree in in-order traversal (Left → Root → Right).

```python
tree.printIN([1, 2, 3, 4, 5, 6, 7])
# Output: 4 2 5 1 6 3 7
```

#### `printPRE(array)`
Prints the tree in pre-order traversal (Root → Left → Right).

```python
tree.printPRE([1, 2, 3, 4, 5, 6, 7])
# Output: 1 2 4 5 3 6 7
```

#### `printPOST(array)`
Prints the tree in post-order traversal (Left → Right → Root).

```python
tree.printPOST([1, 2, 3, 4, 5, 6, 7])
# Output: 4 5 2 6 7 3 1
```

#### `printLVL(array)`
Prints the tree in level-order traversal (Breadth-First Search).

```python
tree.printLVL([1, 2, 3, 4, 5, 6, 7])
# Output: 1 2 3 4 5 6 7
```

---

### Tree Analysis

#### `CountNodes(array)`
Counts the total number of nodes in the tree.

```python
count = tree.CountNodes([1, 2, 3, 4, 5])
# Returns: 5
```

#### `MAXdepth(array)`
Calculates the maximum depth (height) of the tree.

```python
depth = tree.MAXdepth([1, 2, 3, 4, 5])
# Returns: 3
```

#### `MINdepth(array)`
Calculates the minimum depth (shortest path to a leaf).

```python
min_depth = tree.MINdepth([1, 2, 3, 4, None, None, 7])
# Returns: 2
```

#### `getDiameter(array)`
Calculates the diameter (longest path between any two nodes).

```python
diameter = tree.getDiameter([1, 2, 3, 4, 5])
# Returns: 4
```

#### `MAXwidth(array)`
Calculates the maximum width (largest number of nodes at any level).

```python
width = tree.MAXwidth([1, 2, 3, 4, 5, 6, 7])
# Returns: 4
```

#### `findDNST(array)`
Calculates the density of the tree (nodes / height ratio).

```python
density = tree.findDNST([1, 2, 3, 4, 5, 6, 7])
# Returns: 2.33
```

---

### Tree Validation

#### `checkBalanced(array)`
Checks if the tree is height-balanced.

```python
is_balanced = tree.checkBalanced([1, 2, 3, 4, 5, 6, 7])
# Returns: True
```

#### `checkBST(array)`
Validates if the tree is a Binary Search Tree.

```python
is_bst = tree.checkBST([2, 1, 3])
# Returns: True
```

#### `checkAVL(array)`
Checks if the tree is an AVL tree (balanced BST).

```python
is_avl = tree.checkAVL([2, 1, 3])
# Returns: True
```

#### `checkCOM(array)`
Checks if the tree is complete.

```python
is_complete = tree.checkCOM([1, 2, 3, 4, 5, 6])
# Returns: True
```

#### `checkFULL(array)`
Checks if the tree is full (every node has 0 or 2 children).

```python
is_full = tree.checkFULL([1, 2, 3, 4, 5, 6, 7])
# Returns: True
```

#### `checkPRF(array)`
Checks if the tree is perfect (all levels fully filled).

```python
is_perfect = tree.checkPRF([1, 2, 3, 4, 5, 6, 7])
# Returns: True
```

#### `checkSYM(array)`
Checks if the tree is symmetric (mirror image of itself).

```python
is_symmetric = tree.checkSYM([1, 2, 2, 3, 4, 4, 3])
# Returns: True
```

#### `checkFLD(array)`
Checks if the tree is foldable (left and right subtrees are mirrors).

```python
is_foldable = tree.checkFLD([1, 2, 3, 4, None, None, 5])
# Returns: True
```

---

### Tree Modification

#### `invert(array)`
Inverts the tree by swapping left and right children at every node.

```python
tree.invert([1, 2, 3, 4, 5, 6, 7])
# Original: 1 2 3 4 5 6 7
# Inverted: 1 3 2 7 6 5 4
```

#### `addNODE(array, node)`
Adds a new node to the tree at the first available position.

```python
tree.addNODE([1, 2, 3], 4)
# Result: [1, 2, 3, 4]
```

#### `deleteNODE(array, target)`
Deletes a node from the tree and replaces it with the last node.

```python
tree.deleteNODE([1, 2, 3, 4, 5], 3)
# Result: [1, 2, 5, 4]
```

#### `changeNODE(array, prev, new)`
Changes the value of a node from `prev` to `new`.

```python
tree.changeNODE([1, 2, 3, 4, 5], 3, 10)
# Result: [1, 2, 10, 4, 5]
```

#### `margeTREE(arrayA, arrayB)`
Merges two trees by adding corresponding node values.

```python
tree.margeTREE([1, 2, 3], [4, 5, 6])
# Result: [5, 7, 9]
```

#### `FlipCLK(array)`
Flips the tree clockwise.

```python
tree.FlipCLK([1, 2, 3, 4, 5])
```

#### `FlipACLK(array)`
Flips the tree anti-clockwise.

```python
tree.FlipACLK([1, 2, 3, 4, 5])
```

---

### Path Operations

#### `pathSUM(array, target)`
Calculates the sum of the path from root to the target node.

```python
path_sum = tree.pathSUM([1, 2, 3, 4, 5], 5)
# Returns: 8 (1 + 2 + 5)
```

#### `TpathSUM(array, target)`
Returns all paths where the sum equals the target.

```python
paths = tree.TpathSUM([1, 2, 3, 4, 5], 7)
# Returns: [[1, 2, 4], [1, 3, 3]]
```

#### `MAXpathSUM(array)`
Finds the maximum path sum in the tree.

```python
max_sum = tree.MAXpathSUM([1, 2, 3, 4, 5])
# Returns: 15
```

#### `findDST(array, node1, node2)`
Calculates the distance between two nodes.

```python
distance = tree.findDST([1, 2, 3, 4, 5, 6, 7], 4, 7)
# Returns: 4
```

#### `rTOn(array, target)`
Calculates the distance from root to a target node.

```python
distance = tree.rTOn([1, 2, 3, 4, 5], 5)
# Returns: 2
```

---

### Node Operations

#### `getCLD(array, target)`
Returns the children of a target node.

```python
children = tree.getCLD([1, 2, 3, 4, 5, 6, 7], 2)
# Returns: [4, 5]
```

#### `getPNT(array, target)`
Returns the parent of a target node.

```python
parent = tree.getPNT([1, 2, 3, 4, 5], 4)
# Returns: 2
```

#### `getSIB(array)`
Returns a dictionary of all sibling pairs.

```python
siblings = tree.getSIB([1, 2, 3, 4, 5, 6, 7])
# Returns: {4: 5, 5: 4, 6: 7, 7: 6}
```

#### `getLVL(array, target)`
Returns the level (depth) of a target node.

```python
level = tree.getLVL([1, 2, 3, 4, 5], 4)
# Returns: 2
```

#### `KthNODE(array, K)`
Returns the first node at level K.

```python
node = tree.KthNODE([1, 2, 3, 4, 5, 6, 7], 2)
# Returns: 4
```

#### `LCA(array, node1, node2)`
Finds the Lowest Common Ancestor of two nodes.

```python
lca = tree.LCA([1, 2, 3, 4, 5, 6, 7], 4, 5)
# Returns: 2
```

#### `printANC(array, target)`
Prints all ancestors of a target node.

```python
ancestors = tree.printANC([1, 2, 3, 4, 5], 4)
# Returns: [1, 2]
```

#### `printDANC(array, target)`
Prints all descendants of a target node.

```python
descendants = tree.printDANC([1, 2, 3, 4, 5, 6, 7], 2)
# Returns: [4, 5]
```

---

### Tree Views

#### `rightV(array)`
Returns the right side view of the tree.

```python
right_view = tree.rightV([1, 2, 3, 4, 5, 6, 7])
# Returns: [1, 3, 7]
```

#### `leftV(array)`
Returns the left side view of the tree.

```python
left_view = tree.leftV([1, 2, 3, 4, 5, 6, 7])
# Returns: [1, 2, 4]
```

#### `topV(array)`
Returns the top view of the tree.

```python
top_view = tree.topV([1, 2, 3, 4, 5, 6, 7])
# Returns: [4, 2, 1, 3, 7]
```

#### `bottomV(array)`
Returns the bottom view of the tree.

```python
bottom_view = tree.bottomV([1, 2, 3, 4, 5, 6, 7])
# Returns: [4, 5, 6, 7]
```

---

### Comparison Operations

#### `checkSame(arrayA, arrayB)`
Checks if two trees are identical.

```python
is_same = tree.checkSame([1, 2, 3], [1, 2, 3])
# Returns: True
```

#### `checkMIR(arrayA, arrayB)`
Checks if two trees are mirror images.

```python
is_mirror = tree.checkMIR([1, 2, 3], [1, 3, 2])
# Returns: True
```

#### `isSUB(mainTree, subTree)`
Checks if one tree is a subtree of another.

```python
is_subtree = tree.isSUB([1, 2, 3, 4, 5], [2, 4, 5])
# Returns: True
```

#### `FlipEQ(arrayA, arrayB)`
Checks if two trees are flip equivalent.

```python
is_flip_eq = tree.FlipEQ([1, 2, 3], [1, 3, 2])
# Returns: True
```

#### `checkCSN(array, node1, node2)`
Checks if two nodes are cousins (same level, different parents).

```python
are_cousins = tree.checkCSN([1, 2, 3, 4, 5, 6, 7], 4, 6)
# Returns: True
```

#### `leafSM(arrayA, arrayB)`
Checks if two trees have the same leaf nodes.

```python
same_leaves = tree.leafSM([1, 2, 3, 4, 5], [1, 3, 2, 4, 5])
# Returns: True
```

---

### Serialization

#### `Serialize(array)`
Serializes a tree into a list format.

```python
serialized = tree.Serialize([1, 2, 3, 4, 5])
# Returns: [1, 2, 3, 4, 5]
```

#### `Deserialize(array)`
Deserializes a list back into a tree structure.

```python
tree.Deserialize([1, 2, 3, 4, 5])
# Reconstructs the tree and prints it
```

---

### Special Validations

#### `CLDsum(array)`
Checks if the tree satisfies the Children Sum Property (node value = sum of children).

```python
has_cld_sum = tree.CLDsum([10, 5, 5, 2, 3, 2, 3])
# Returns: True
```

#### `findLv(array)`
Finds the largest value in the tree.

```python
max_val = tree.findLv([1, 2, 3, 4, 5])
# Returns: 5
```

#### `findSv(array)`
Finds the smallest value in the tree.

```python
min_val = tree.findSv([1, 2, 3, 4, 5])
# Returns: 1
```

---

##  Examples

### Example 1: Basic Tree Operations

```python
from binary_tree import BinaryTree

tree = BinaryTree()
arr = [1, 2, 3, 4, 5, 6, 7]

# Create and traverse
tree.printLVL(arr)  # 1 2 3 4 5 6 7

# Get properties
print(f"Nodes: {tree.CountNodes(arr)}")        # 7
print(f"Height: {tree.MAXdepth(arr)}")         # 3
print(f"Balanced: {tree.checkBalanced(arr)}")  # True
```

### Example 2: Path Finding

```python
arr = [5, 4, 8, 11, None, 13, 4, 7, 2, None, None, None, 1]

# Find path sum to target
path_sum = tree.pathSUM(arr, 2)
print(f"Path sum to 2: {path_sum}")

# Find all paths with target sum
paths = tree.TpathSUM(arr, 22)
print(f"Paths with sum 22: {paths}")

# Maximum path sum
max_sum = tree.MAXpathSUM(arr)
print(f"Maximum path sum: {max_sum}")
```

### Example 3: Tree Validation

```python
bst = [2, 1, 3]
complete = [1, 2, 3, 4, 5]
symmetric = [1, 2, 2, 3, 4, 4, 3]

print(f"Is BST: {tree.checkBST(bst)}")              # True
print(f"Is Complete: {tree.checkCOM(complete)}")    # True
print(f"Is Symmetric: {tree.checkSYM(symmetric)}")  # True
```

### Example 4: Tree Modifications

```python
arr = [1, 2, 3, 4, 5, 6, 7]

# Invert the tree
tree.invert(arr)

# Merge two trees
tree1 = [1, 3, 2, 5]
tree2 = [2, 1, 3, None, 4, None, 7]
tree.margeTREE(tree1, tree2)

# Add and delete nodes
tree.addNODE(arr, 8)
tree.deleteNODE(arr, 4)
```

### Example 5: Advanced Operations

```python
arr = [1, 2, 3, 4, 5, 6, 7]

# Find LCA
lca = tree.LCA(arr, 4, 5)
print(f"LCA of 4 and 5: {lca}")

# Get different views
print(f"Right view: {tree.rightV(arr)}")
print(f"Top view: {tree.topV(arr)}")

# Check relationships
are_cousins = tree.checkCSN(arr, 4, 6)
print(f"Are 4 and 6 cousins: {are_cousins}")
```

---

##  Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes, please open an issue first to discuss what you would like to change.

### Guidelines
1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## Author

**Amir Sakib Saad**

- Email: amirsakib16@gmail.com

---

##  Acknowledgments

- Thanks to all contributors who have helped this project grow
- Inspired by classic data structures and algorithms courses
- Built with passion for clean, efficient code

---

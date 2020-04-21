# Binary Tree
* A tree with at most two children <br/>
![Image of Yaktocat](https://www.geeksforgeeks.org/wp-content/uploads/binary-tree-to-DLL.png)

## Components
1. Data
2. Pointer to left child
3. Pointer to right child

## Terminology 
Root: topmost node <br/>
Children: elements under a given element <br/>
Ancestors: elements that are on top of the node <br/>
Leaves: elements with no children/bottom of tree <br/>

## Advantages
* Store info that naturally forms a hierarchy ex/ file system
* Moderate access/search time (quicker than Linked List and slower than arrays)
* Moderate insertion/deletion (quicker than Arrays and slower than Unordered Linked Lists)
* No upper limit on number of nodes (compared to linked lists)

## Main Applications / Uses
1. Manipulate hierarchical data.
2. Make information easy to search (see tree traversal).
3. Manipulate sorted lists of data.
4. As a workflow for compositing digital images for visual effects.
5. Router algorithms
6. Form of a multi-stage decision-making (see business chess).

## Properties 
* Maximum Number of Nodes at a Given Level (n): 2^n-1
* Maximum Number of Nodes in a Given Height (h): 2h - 1
* Minimum Height with **n** nodes: log2(𝑛+1)−1
* Minimum Height **L** leaves has at least Log2L + 1 levels

## Implementation
### Node
```
# A Python class that represents an individual node in a Binary Tree 
class Node: 
    def __init__(self,key): 
        self.left = None
        self.right = None
        self.val = key 
```

```
// Class containing left and right child of current  node and key value 
class Node  { 
    int key; 
    Node left, right; 
  
    public Node(int item) 
    { 
        key = item; 
        left = right = null; 
    } 
}
```

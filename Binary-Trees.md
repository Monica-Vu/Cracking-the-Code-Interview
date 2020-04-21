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
Depth: length from one node to another
```
    int depth(Node u) {
        int d = 0;
        while (u != r) {
            u = u.parent;
            d++;
        }
        return d;
    }
```

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
    class BTNode<Node extends BTNode<Node>> {
        Node left;
        Node right;
        Node parent;    
    }
```

### Binary Tree 
```
  Node r;
```

### Find number of nodes in a tree
```
    int size(Node u) {
        if (u == nil) return 0;
        return 1 + size(u.left) + size(u.right);
    }
```

### Find tree height 
```
    int height(Node u) {
        if (u == nil) return -1;
        return 1 + Math.max(height(u.left), height(u.right));
    }
```

### Traversing Binary Trees
```
    void traverse(Node u) {
        if (u == nil) return;
        traverse(u.left);
        traverse(u.right);
    }
```
* Problem: height can be tall, which can can a stack overflow due to recursion 

### Traversing Binary Trees (No Recursion)
* Parent -> Left -> Right -> Left -> Right -> . . . -> Parent 
```
    void traverse2() {
        Node u = r, prev = nil, next;
        while (u != nil) {
            if (prev == u.parent) {
                if (u.left != nil) next = u.left;
                else if (u.right != nil) next = u.right;
                else next = u.parent;
            } else if (prev == u.left) {
                if (u.right != nil) next = u.right;
                else next = u.parent;
            } else {
                next = u.parent;
            }
            prev = u;
            u = next;
        }
    }
```

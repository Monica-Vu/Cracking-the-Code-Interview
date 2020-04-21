# LINKED LISTS
* A dynamic data structure can grow & shrink dynamically using nodes 
* Each node has a pointer to the next node and data 

## Disadvantages
* Does not allow direct access to individual elements (need to start at head or tail) and follow the reference
* Use more memory than array (4 extra bytes on 32-bit system)

## SINGLY
* Each node has a pointer to the next node
![alt text](https://www.java2novice.com/images/linked_list.png)

### Implementation 
#### NODE
```
// JAVA
//  Linked List Class 
class LinkedList  { 
    Node head;  // head of list 
  
    /* Node Class */
    class Node  { 
        int data; 
        Node next; 
           
        // Constructor to create a new node 
        Node(int d) {data = d; next = null; } 
    } 
}

```

```
# Python
# Node class 
class Node: 
  
    # Function to initialize the node object 
    def __init__(self, data): 
        self.data = data  # Assign data 
        self.next = None  # Initialize next as null 
  
# Linked List class 
class LinkedList: 
    
    # Function to initialize the Linked List object 
    def __init__(self):  
        self.head = None

```
#### INSERTING AT THE START
1. Allocate the new node and insert data
2. Set the new node's next as "head"
3. Set head to new node 

```
/* This function is in LinkedList class. Inserts a  new Node at front of the list. This method is  
   defined inside LinkedList class shown above */

public void push(int new_data) { 
    /* 1 & 2: Allocate the Node &   Put in the data*/
    Node new_node = new Node(new_data); 
  
    /* 3. Make next of new Node as head */
    new_node.next = head; 
  
    /* 4. Move the head to point to new Node */
    head = new_node; 
}
```

```
# This function is in LinkedList class 
# Function to insert a new node at the beginning 
def push(self, new_data): 
    # 1 & 2: Allocate the Node & put in the data 
    new_node = Node(new_data) 
          
    # 3. Make next of new Node as head 
    new_node.next = self.head 
          
    # 4. Move the head to point to new Node  
    self.head = new_node

```


## DOUBLY
* Each node has a pointer to the next node and the previous node 
![alt text](https://media.geeksforgeeks.org/wp-content/cdn-uploads/gq/2014/03/DLL1.png)

## CIRCULAR
* Last node points to head of list 


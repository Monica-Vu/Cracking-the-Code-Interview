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
    // Node tail --> this is optional 
  
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
Time Complexity: O(1) 

#### INSERTING AFTER A GIVEN NODE
1. Make new node and put data 
2. Check if previous is null. Other modification may include having to figure on based on a value (so no prev_node to based off).
3. Set the new node's next as the previous node's next
4. Set previous's node next as new node 

```
/* This function is in LinkedList class.  Inserts a new node after the given prev_node. This method is  defined inside LinkedList class shown above */

public void insertAfter(Node prev_node, int new_data) { 
	/* 1. Check if the given Node is null */
	if (prev_node == null)  { 
		System.out.println("The given previous node cannot be null"); 
		return; 
	} 

	/* 2. Allocate the Node & 3. Put in the data*/
	Node new_node = new Node(new_data); 

	/* 4. Make next of new Node as next of prev_node */
	new_node.next = prev_node.next; 

	/* 5. make next of prev_node as new_node */
	prev_node.next = new_node; 
} 
```

#### INSERTING AT THE END OF LINKED LIST
```
# This function is in LinkedList class. 
# Inserts a new node after the given prev_node. This method is  
# defined inside LinkedList class shown above */ 
def insertAfter(self, prev_node, new_data): 
  
    # 1. check if the given prev_node exists 
    if prev_node is None: 
        print "The given previous node must inLinkedList."
        return
  
    #  2. Create new node & 
    #  3. Put in the data 
    new_node = Node(new_data) 
  
    # 4. Make next of new Node as next of prev_node  
    new_node.next = prev_node.next
  
    # 5. make next of prev_node as new_node  
    prev_node.next = new_node

```
Time Complexity: O(1) 

```
/* Appends a new node at the end. This method is  defined inside LinkedList class shown above */
public void append(int new_data)  { 
	/* 1. Allocate the Node & 2. Put in the data  3. Set next as null (note: this is  automatically done in our code */
	Node new_node = new Node(new_data); 

	/* 4. If the Linked List is empty, then make the 
		new node as head */
	if (head == null) 
	{ 
		head = new Node(new_data); 
		return; 
	} 

	/* 4. This new node is going to be the last node, so 
		make next of it as null */
	new_node.next = null; 

	/* 5. Else traverse till the last node */
	Node last = head; 
	while (last.next != null) 
		last = last.next; 

	/* 6. Change the next of last node */
	last.next = new_node; 
	return; 
} 
```

```
# This function is defined in Linked List class 
# Appends a new node at the end.  This method is 
#  defined inside LinkedList class shown above */ 
def append(self, new_data): 
 
   # 1. Create a new node 
   # 2. Put in the data 
   # 3. Set next as None 
   new_node = Node(new_data) 
 
   # 4. If the Linked List is empty, then make the 
   #    new node as head 
   if self.head is None: 
        self.head = new_node 
        return
 
   # 5. Else traverse till the last node 
   last = self.head 
   while (last.next): 
       last = last.next
 
   # 6. Change the next of last node 
   last.next =  new_node 
```

Time Complexity: O(n) because it needs to loop through all the nodes of the list or O(1) if we had a tail 

#### DELETING A NODE
1. Find the previous node of the node to be deleted
2. Change the next of previous
3. Free memory for node to be deleted 
![alt text](https://media.geeksforgeeks.org/wp-content/cdn-uploads/gq/2014/05/Linkedlist_deletion.png)

## DOUBLY
* Each node has a pointer to the next node and the previous node 
![alt text](https://media.geeksforgeeks.org/wp-content/cdn-uploads/gq/2014/03/DLL1.png)

## CIRCULAR
* Last node points to head of list 

## USES
* Arrays are static (can’t easily be extended or reduce to fit data set) & expensive to maintain so we use linked list instead to save space 

## SOURCES
https://www.cs.cmu.edu/~adamchik/15-121/lectures/Linked%20Lists/linked%20lists.html
https://www.geeksforgeeks.org/linked-list-set-2-inserting-a-node/



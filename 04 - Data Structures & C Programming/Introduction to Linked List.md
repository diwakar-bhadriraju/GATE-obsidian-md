---
title: "Linked List Notes for GATE Exam [2024]"
subject: "Data Structures & C Programming"
topic: "Linked List"
source: "https://www.geeksforgeeks.org/dsa/linked-list-notes-for-gate-exam/#what-is-linked-list"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Data Structures & C Programming/Linked List"
tags:
  - gate/cs
  - subject/data-structures-c-programming
  - topic/linked-list
---


> [!abstract] Linked List Notes for GATE Exam [2024]
> 
> **Subject:** `Data Structures & C Programming` &nbsp;|&nbsp; **Topic:** `Linked List`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dsa/linked-list-notes-for-gate-exam/#what-is-linked-list)

---

# Linked List Notes for GATE Exam [2024]

The "Linked List Notes for GATE Exam" is a comprehensive resource designed to aid students in preparing for the Graduate Aptitude Test in Engineering (GATE). Focused specifically on linked lists, a fundamental data structure in computer science, these notes offer a detailed and structured approach to mastering this subject within the context of the GATE examination.
Table of Content
- [What is a Linked List?](#what-is-linked-list)
- [Singly Linked List:](#singly-linked-list)
- [Doubly Linked List:](#doubly-linked-list)
- [Circular Linked List:](#circular-linked-list)
- [Applications of Linked List:](#applications-of-linked-list)
- [Advantages of Linked Lists:](#advantages-of-linked-lists)
- [Disadvantages of Linked Lists:](#disadvantages-of-linked-lists)
- [Gate Archives on Linked List:](#gate-archives-on-linked-list)
## What is a Linked List?
> A [**linked list**](https://www.geeksforgeeks.org/dsa/linked-list-data-structure/) is a **linear** data structure, in which the elements are not stored at contiguous memory locations. Linked list consists of nodes where each node contains a data field and a reference(link) to the next node in the list.
The elements in a linked list are linked using pointers as shown in the below image:
![Linked-List-Data-Structure](assets/Linked-List-Data-Structure-768-266decc6ab.png)
Linked-List-Data-Structure
## [Singly Linked List:](https://www.geeksforgeeks.org/dsa/singly-linked-list-tutorial/)
> **A** **singly linked list** **is a linear data structure in which the elements are not stored in contiguous memory locations and each element is connected only to its next element using a pointer.**
The elements in a linked list are linked using pointers to the next node as shown in the below image:
![LLdrawio](assets/LLdrawio-768-56f67d184a.png)
Singly Linked List
**Operations on Singly Linked List:**
- **Insertion at the beginning of the Linked List:** To insert a node at the beginning of the Linked List, we change the next pointer of the new node to the current head and make the new node as the current head. Time Complexity: **O(1)**
- **Insertion at the end or after a given node:** To insert a node after a given node, we need to update the next pointer of the new node to the next pointer of the given node and update the next pointer of the given node to the new node. Time Complexity: **O(N)** as in the worst case we may traverse through all the nodes of the linked list.
- **Searching an element:** We can search a node by traversing through the linked list and comparing the nodes one by one. Time Complexity: **O(N)**
- **Find length of the Linked List:** We can find the length of the linked list by traversing through the linked list and maintaining the count of nodes. Time Complexity: **O(N)**
- **Reverse a Linked List:** We can reverse a linked list using three pointers **curr**, **prev,** and **next**to keep track of nodes to update reverse links**.** Time Complexity: **O(N)**
- **Deletion at the beginning of the Linked List:** To delete a node from the beginning of the Linked List, we can change the head to the next of the current head and delete the previous head. Time Complexity: **O(1)**
- **Deletion at the end or after a given node:** To delete a node after a given node, we need to update the next pointer of the given node to point to the node which is present after the node to be deleted. Time Complexity: **O(N)** as in the worst case we may traverse through all the nodes of the linked list.
## [Doubly Linked List:](https://www.geeksforgeeks.org/dsa/linked-list-data-structure/)
> A **doubly linked list** (DLL) is a special type of linked list in which each node contains a pointer to the previous node as well as the next node of the linked list.
The elements in a linked list are linked using pointers to the next node as well as to the previous node as shown in the below image:
![DLL1](assets/DLL1-768-ae8ab04329.png)
Doubly Linked List
All operations of **Doubly linked list** are same as of Singly Linked List, except that we need to update the previous pointers along with the next pointers whenever we insert or delete a node.
## [Circular Linked List:](https://www.geeksforgeeks.org/dsa/circular-linked-list/)
The**circular linked list** is a linked list where all nodes are connected to form a circle. In a circular linked list, the first node and the last node are connected to each other which forms a circle. There is no NULL at the end.
The elements in a linked list are linked using pointers to the next node with the last node pointing to the head of the linked list as shown in the below image:
![CircularSinglyLinkedList-660x172](assets/CircularSinglyLinkedList-660x172-27fc68deb5.png)
Circular Singly Linked List
All operations of Circular Singly Linked List are same as of Singly Linked List.
There are two types of Circular Linked List:
- **Circular singly linked list:**In a circular Singly linked list, the last node of the list contains a pointer to the first node of the list. We traverse the circular singly linked list until we reach the same node where we started. The circular singly linked list has no beginning or end. No null value is present in the next part of any of the nodes.
- **Circular Doubly linked list:** Circular Doubly Linked List has properties of both doubly linked list and circular linked list in which two consecutive elements are linked or connected by the previous and next pointer and the last node points to the first node by the next pointer and also the first node points to the last node by the previous pointer.
![Circulardoublylinkedlist-660x155](assets/Circulardoublylinkedlist-660x155-f257ef4fc4.png)
Circular Doubly Linked List
**Note:** Unlike other types of Linked Lists, Circular Doubly Linked List takes **O(1)** time for insertion or deletion at the end of the Linked List.
## Applications of Linked List:
- **Image viewer** – Previous and next images are linked and can be accessed by the next and previous buttons.
- **Previous and next page in a web browser** – We can access the previous and next URL searched in a web browser by pressing the back and next buttons since they are linked as a linked list.
- **Music Player** – Songs in the music player are linked to the previous and next songs. So you can play songs either from starting or ending of the list.
- **GPS navigation systems**- Linked lists can be used to store and manage a list of locations and routes, allowing users to easily navigate to their desired destination.
## Advantages of Linked Lists:
- **Dynamic Size:**Linked lists can grow or shrink dynamically, as memory allocation is done at runtime.
- **Insertion and Deletion:**Adding or removing elements from a linked list is efficient, especially for large lists.
- **Flexibility:** Linked lists can be easily reorganized and modified without requiring a contiguous block of memory.
## Disadvantages of Linked Lists:
- **Random Access:**Unlike arrays, linked lists do not allow direct access to elements by index. Traversal is required to reach a specific node.
- **Extra Memory:** Linked lists require additional memory for storing the pointers, compared to arrays.
## Gate Archives on Linked List:
**Q1.** Consider the problem of reversing a singly linked list. To take an example, given the linked list below, 
![ques15](assets/ques15-2308312497.jpg)
the reversed linked list should look like 
![152](assets/152-aa79ee2a32.jpg)
Which one of the following statements is TRUE about the time complexity of algorithms that solve the above problem in O(1) space?
**(A)** The best algorithm for the problem takes Θ(N) time in the worst case
**(B)** The best algorithm for the problem takes Θ(N \* logN) time in the worst case. 
**(C)** The best algorithm for the problem takes Θ(N\*N) time in the worst case
**(D)** It is not possible to reverse a singly linked list in O(1) space. 
> **Answer:** **(A)**
> **Explanation:** The given linked list is a reverse linked list and the best algorithm in reverse linked list takes time in the worst case. So, option A is the correct answer. 
**Q2.** What is the worst-case time complexity of inserting n elements into an empty linked list, if the linked list needs to be maintained in sorted order?
**(A)** Θ(n)
**(B)** Θ(n log n)
**(C)** Θ(n2)
**(D)** Θ(1)
> **Answer:** **(C)**
> **Explanation:** If we want to insert n elements into an empty linked list that needs to be maintained in sorted order, the worst-case time complexity would be O(n^2). This is because we would need to traverse the list for each element we want to insert, to find the correct position for the element in the sorted list.
**Q3.** What does the following function do for a given Linked List with first node as **head**?
```
void fun1(struct node* head)
{
  if(head == NULL)
    return;
  fun1(head->next);
  printf("%d  ", head->data);
}
```
**(A)** Prints all nodes of linked list
**(B)** Prints all nodes of linked list in reverse order
**(C)** Prints alternate nodes of Linked List
**(D)** Prints alternate nodes in reverse order
> **Answer: (B)**
> **Explanation:** It first checks if the head is NULL, and if it is, it returns without doing anything. Otherwise, it calls the **fun1** function recursively with the next node in the linked list (**head->next**). This continues until the last node is reached, which is the node whose **next** pointer is **NULL**. At this point, the function starts returning, and as it returns it prints the value of each node in the linked list starting from the last node, working its way backwards to the first node. This is achieved through the **printf** statement which prints the value of **head->data**.
**Q4.** Which of the following points is/are true about Linked List data structure when it is compared with array?
**(A)** Arrays have better cache locality that can make them better in terms of performance.
**(B)** It is easy to insert and delete elements in Linked List
**(C)** Random access is not allowed in a typical implementation of Linked Lists
**(D)** The size of array has to be pre-decided, linked lists can change their size any time.
**(E)** All of the above
> **Answer: (E)**
> **Explanation:** The following points are true when comparing Linked List data structure with an array:
>
> - Insertion and deletion: Linked lists allow for efficient insertion and deletion operations at any point in the list, as they involve simply adjusting pointers, while in an array, these operations can be expensive as all the elements after the insertion or deletion point need to be shifted.
> - Memory allocation: Linked lists use dynamic memory allocation, so they can grow or shrink as needed, while arrays have a fixed size and need to be allocated a contiguous block of memory upfront.
> - Access time: Arrays provide constant-time access to any element in the array (assuming the index is known), while accessing an element in a linked list takes linear time proportional to the number of elements in the list, as the list needs to be traversed from the beginning to find the desired element.
> - Random access: Arrays support random access, which means that we can directly access any element in the array with its index, while linked lists do not support random access and we need to traverse the list to find a specific element.
**Q5.** Consider the following function that takes reference to head of a Doubly Linked List as parameter. Assume that a node of doubly linked list has previous pointer as **prev**and next pointer as **next**.
````cpp
#include <iostream>
using namespace std;
class Node {
public:
    int data;
    Node* prev;
    Node* next;
    Node(int data)
    {
        this->data = data;
        this->prev = nullptr;
        this->next = nullptr;
    }
};
void fun(Node** head_ref)
{
    Node* temp = nullptr;
    Node* current = *head_ref;
    while (current != nullptr) {
        temp = current->prev;
        current->prev = current->next;
        current->next = temp;
        current = current->prev;
    }
    if (temp != nullptr)
        *head_ref = temp->prev;
}
int main()
{
    // Create a linked list with sample nodes
    Node* head = new Node(1);
    Node* second = new Node(2);
    Node* third = new Node(3);
    head->next = second;
    second->prev = head;
    second->next = third;
    third->prev = second;
    // Call the function
    Node* headRef[] = { head };
    fun(headRef);
    // Print the reversed list
    Node* current = headRef[0];
    while (current != nullptr) {
        cout << current->data << " ";
        current = current->next;
    }
    return 0;
}
````
````c
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node* prev;
    struct Node* next;
};
typedef struct Node Node;
void fun(Node** head_ref)
{
    Node* temp = NULL;
    Node* current = *head_ref;
    while (current != NULL) {
        temp = current->prev;
        current->prev = current->next;
        current->next = temp;
        current = current->prev;
    }
    if (temp != NULL)
        *head_ref = temp->prev;
}
int main()
{
    // Create a linked list with sample nodes
    Node* head = (Node*)malloc(sizeof(Node));
    Node* second = (Node*)malloc(sizeof(Node));
    Node* third = (Node*)malloc(sizeof(Node));
    head->data = 1;
    head->next = second;
    head->prev = NULL;
    second->data = 2;
    second->next = third;
    second->prev = head;
    third->data = 3;
    third->next = NULL;
    third->prev = second;
    // Call the function
    Node* headRef[] = { head };
    fun(headRef);
    // Print the reversed list
    Node* current = headRef[0];
    while (current != NULL) {
        printf("%d ", current->data);
        current = current->next;
    }
    // Free memory
    free(head);
    free(second);
    free(third);
    return 0;
}
````
````java
class Node {
    int data;
    Node prev;
    Node next;
    public Node(int data)
    {
        this.data = data;
        this.prev = null;
        this.next = null;
    }
}
public class Main {
    static void fun(Node[] head_ref)
    {
        Node temp = null;
        Node current = head_ref[0];
        while (current != null) {
            temp = current.prev;
            current.prev = current.next;
            current.next = temp;
            current = current.prev;
        }
        if (temp != null)
            head_ref[0] = temp.prev;
    }
    public static void main(String[] args)
    {
        // Create a linked list with sample nodes
        Node head = new Node(1);
        Node second = new Node(2);
        Node third = new Node(3);
        head.next = second;
        second.prev = head;
        second.next = third;
        third.prev = second;
        // Call the function
        Node[] headRef = { head };
        fun(headRef);
        // Print the reversed list
        Node current = headRef[0];
        while (current != null) {
            System.out.print(current.data + " ");
            current = current.next;
        }
    }
}
````
````python3
class Node:
    def __init__(self, data):
        self.data = data
        self.prev = None
        self.next = None
def fun(head_ref):
    temp = None
    current = head_ref[0]
    while current is not None:
        temp = current.prev
        current.prev = current.next
        current.next = temp
        current = current.prev
    if temp is not None:
        head_ref[0] = temp.prev
if __name__ == "__main__":
    # Create a linked list with sample nodes
    head = Node(1)
    second = Node(2)
    third = Node(3)
    head.next = second
    second.prev = head
    second.next = third
    third.prev = second
    # Call the function
    headRef = [head]
    fun(headRef)
    # Print the reversed list
    current = headRef[0]
    while current is not None:
        print(current.data, end=" ")
        current = current.next
# this code is contributed by Prachi
````
````javascript
class Node {
    constructor(data) {
        this.data = data;
        this.prev = null;
        this.next = null;
    }
}
function fun(headRef) {
    let temp = null;
    let current = headRef[0];
    while (current !== null) {
        temp = current.prev;
        current.prev = current.next;
        current.next = temp;
        current = current.prev;
    }
    if (temp !== null)
        headRef[0] = temp.prev;
}
// Create a linked list with sample nodes
let head = new Node(1);
let second = new Node(2);
let third = new Node(3);
head.next = second;
second.prev = head;
second.next = third;
third.prev = second;
// Call the function
let headRef = [head];
fun(headRef);
// Print the reversed list
let current = headRef[0];
while (current !== null) {
    console.log(current.data);
    current = current.next;
}
````
Assume that reference of head of following doubly linked list is passed to above function 1 <--> 2 <--> 3 <--> 4 <--> 5 <-->6. What should be the modified linked list after the function call?
**(A)** 2 <--> 1 <--> 4 <--> 3 <--> 6 <-->5
**(B)** 5 <--> 4 <--> 3 <--> 2 <--> 1 <-->6
**(C)** 6 <--> 5 <--> 4 <--> 3 <--> 2 <--> 1
**(D)** 6 <--> 5 <--> 4 <--> 3 <--> 1 <--> 2
> **Answer: (C)**
> **Explanation:** This function fun takes a double pointer to the head of a doubly linked list as its argument and reverses the order of the nodes in the list.
**Q6.** Which of the following sorting algorithms can be used to sort a random linked list with minimum time complexity?
**(A)** Insertion Sort
**(B)** Quick Sort
**(C)** Heap Sort
**(D)** Merge Sort
> **Answer: (D)**
> **Explanation:** Both Merge sort and Insertion sort can be used for linked lists. The slow random-access performance of a linked list makes other algorithms (such as quicksort) perform poorly, and others (such as heapsort) completely impossible. Since worst case time complexity of Merge Sort is O(nLogn) and Insertion sort is O(n^2), merge sort is preferred. See following for implementation of merge sort using Linked List.
**Q7.** The following function reverse() is supposed to reverse a singly linked list. There is one line missing at the end of the function.
````cpp
#include <iostream>
/* Link list node */
struct node
{
    int data;
    struct node* next;
};
/* Function to reverse a linked list */
static void reverse(struct node** head_ref)
{
    struct node* prev = nullptr;
    struct node* current = *head_ref;
    struct node* next;
    while (current != nullptr)
    {
        next = current->next;
        current->next = prev;
        prev = current;
        current = next;
    }
    *head_ref = prev; // Update the head pointer
}
int main()
{
    // Example usage of the reverse function
    struct node* head = new node{1, new node{2, new node{3, nullptr}}};
    std::cout << "Original list: ";
    for (struct node* current = head; current != nullptr; current = current->next)
    {
        std::cout << current->data << " ";
    }
    std::cout << std::endl;
    reverse(&head);
    std::cout << "Reversed list: ";
    for (struct node* current = head; current != nullptr; current = current->next)
    {
        std::cout << current->data << " ";
    }
    std::cout << std::endl;
    // Free memory (assuming a real-world scenario)
    while (head != nullptr)
    {
        struct node* temp = head;
        head = head->next;
        delete temp;
    }
    return 0;
}
````
````c
/* Link list node */
struct node
{
    int data;
    struct node* next;
};
/* head_ref is a double pointer which points to head (or start) pointer
  of linked list */
static void reverse(struct node** head_ref)
{
    struct node* prev   = NULL;
    struct node* current = *head_ref;
    struct node* next;
    while (current != NULL)
    {
        next  = current->next;
        current->next = prev;
        prev = current;
        current = next;
    }
    /*ADD A STATEMENT HERE*/
}
````
````java
class Main {
    /* Link list node */
    static class Node {
        int data;
        Node next;
        Node(int data) {
            this.data = data;
            this.next = null;
        }
    }
    /* Function to reverse a linked list */
    static void reverse(Node head_ref) {
        Node prev = null;
        Node current = head_ref;
        Node next;
        while (current != null) {
            next = current.next;
            current.next = prev;
            prev = current;
            current = next;
        }
        head_ref = prev; // Update the head pointer
    }
    public static void main(String[] args) {
        // Example usage of the reverse function
        Node head = new Node(1);
        head.next = new Node(2);
        head.next.next = new Node(3);
        // Print original list
        System.out.print("Original list: ");
        Node current = head;
        while (current != null) {
            System.out.print(current.data + " ");
            current = current.next;
        }
        System.out.println();
        // Reverse the linked list
        reverse(head);
        // Print reversed list
        System.out.print("Reversed list: ");
        current = head;
        while (current != null) {
            System.out.print(current.data + " ");
            current = current.next;
        }
        System.out.println();
        // Free memory (assuming a real-world scenario)
        while (head != null) {
            Node temp = head;
            head = head.next;
            temp = null;
        }
    }
}
//This code is contributed by utkarsh.
````
````python3
class Node:
    def __init__(self, data):
        """
        Initialize a node with given data and next pointer.
        Parameters:
            data: The data to be stored in the node.
        """
        self.data = data
        self.next = None
def reverse(head):
    """
    Function to reverse a linked list.
    Parameters:
        head (Node): Reference to the head node of the linked list.
    Returns:
        Node: Reference to the new head node of the reversed linked list.
    """
    prev = None  # Initialize a pointer to previous node as None
    current = head  # Initialize current pointer to the head of the list
    while current is not None:
        next_node = current.next  # Store the next node
        current.next = prev  # Reverse the link of current node
        prev = current  # Move pointers one position ahead
        current = next_node
    return prev  # Return new head of the reversed list
if __name__ == "__main__":
    # Example usage of the reverse function
    head = Node(1)
    head.next = Node(2)
    head.next.next = Node(3)
    # Print original list
    print("Original list: ", end="")
    current = head
    while current is not None:
        print(current.data, end=" ")
        current = current.next
    print()
    # Reverse the list
    head = reverse(head)
    # Print reversed list
    print("Reversed list: ", end="")
    current = head
    while current is not None:
        print(current.data, end=" ")
        current = current.next
    print()
    # Free memory (assuming a real-world scenario)
    while head is not None:
        temp = head
        head = head.next
        del temp  # Delete the node and free memory
````
````javascript
class Node {
    constructor(data) {
        this.data = data;
        this.next = null;
    }
}
function reverse(head) {
    let prev = null;
    let current = head;
    while (current !== null) {
        const nextNode = current.next;
        current.next = prev;
        prev = current;
        current = nextNode;
    }
    return prev;
}
// Example usage of the reverse function
let head = new Node(1);
head.next = new Node(2);
head.next.next = new Node(3);
// Print original list
process.stdout.write("Original list: ");
let current = head;
while (current !== null) {
    process.stdout.write(current.data + " ");
    current = current.next;
}
console.log();
// Reverse the list
head = reverse(head);
// Print reversed list
process.stdout.write("Reversed list: ");
current = head;
while (current !== null) {
    process.stdout.write(current.data + " ");
    current = current.next;
}
console.log();
// Free memory (assuming a real-world scenario)
while (head !== null) {
    const temp = head;
    head = head.next;
    // Delete the node (not needed in JavaScript) and free memory
}
````
What should be added in place of "/\*ADD A STATEMENT HERE\*/", so that the function correctly reverses a linked list.
**(A)** \*head\_ref = prev;
**(B)** \*head\_ref = current;
**(C)** \*head\_ref = next;
**(D)** \*head\_ref = NULL;
> **Answer: (A)**
> **Explanation:** The statement to update the head pointer could be as follows
> \*head\_ref = prev;
> This statement sets the value of **\*head\_ref** (which is a double pointer) to the value of **prev**, which is the new head of the reversed list.
**Q8.** What is the output of following function in which start is pointing to the first node of the following linked list 1->2->3->4->5->6 ?
````cpp
#include <iostream>
// Linked list node
struct node
{
    int data;
    struct node* next;
};
// Function to traverse and print the linked list in a specific pattern
void fun(struct node* start)
{
    if (start == nullptr)
        return;
    std::cout << start->data << " "; // Print the current node's data
    if (start->next != nullptr && start->next->next != nullptr)
        fun(start->next->next); // Recursive call for every second node
    std::cout << start->data << " "; // Print the current node's data again
}
int main()
{
    // Example usage
    struct node* head = new node{1, nullptr};
    head->next = new node{2, nullptr};
    head->next->next = new node{3, nullptr};
    head->next->next->next = new node{4, nullptr};
    head->next->next->next->next = new node{5, nullptr};
    std::cout << "Linked List in the specified pattern: ";
    fun(head);
    std::cout << std::endl;
    // Deallocate memory
    while (head != nullptr)
    {
        struct node* next_node = head->next;
        delete head;
        head = next_node;
    }
    return 0;
}
````
````c
#include <stdio.h>
#include <stdlib.h>
// Linked list node
struct node {
    int data;
    struct node* next;
};
// Function to traverse and print the linked list in a specific pattern
void fun(struct node* start) {
    if (start == NULL)
        return;
    printf("%d ", start->data); // Print the current node's data
    if (start->next != NULL && start->next->next != NULL)
        fun(start->next->next); // Recursive call for every second node
    printf("%d ", start->data); // Print the current node's data again
}
int main() {
    // Example usage
    struct node* head = (struct node*)malloc(sizeof(struct node));
    head->data = 1;
    head->next = (struct node*)malloc(sizeof(struct node));
    head->next->data = 2;
    head->next->next = (struct node*)malloc(sizeof(struct node));
    head->next->next->data = 3;
    head->next->next->next = (struct node*)malloc(sizeof(struct node));
    head->next->next->next->data = 4;
    head->next->next->next->next = (struct node*)malloc(sizeof(struct node));
    head->next->next->next->next->data = 5;
    head->next->next->next->next->next = NULL;
    printf("Linked List in the specified pattern: ");
    fun(head);
    printf("\n");
    // Deallocate memory
    struct node* current = head;
    struct node* next_node;
    while (current != NULL) {
        next_node = current->next;
        free(current);
        current = next_node;
    }
    return 0;
}
````
````java
class Node {
    int data;
    Node next;
    Node(int data) {
        this.data = data;
        this.next = null;
    }
}
public class LinkedListTraversal {
    // Function to traverse and print the linked list in a specific pattern
    static void fun(Node start) {
        if (start == null)
            return;
        System.out.print(start.data + " "); // Print the current node's data
        if (start.next != null && start.next.next != null)
            fun(start.next.next); // Recursive call for every second node
        System.out.print(start.data + " "); // Print the current node's data again
    }
    public static void main(String[] args) {
        // Example usage
        Node head = new Node(1);
        head.next = new Node(2);
        head.next.next = new Node(3);
        head.next.next.next = new Node(4);
        head.next.next.next.next = new Node(5);
        System.out.print("Linked List in the specified pattern: ");
        fun(head);
        System.out.println();
        // Deallocate memory (Java handles garbage collection automatically)
    }
}
// This code is contributed by Rambabu
````
````python3
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None
# Function to traverse and print the linked list in a specific pattern
def fun(start):
    if start is None:
        return
    print(start.data, end=" ")  # Print the current node's data
    if start.next is not None and start.next.next is not None:
        fun(start.next.next)  # Recursive call for every second node
    print(start.data, end=" ")  # Print the current node's data again
# Example usage
if __name__ == "__main__":
    # Create the linked list
    head = Node(1)
    head.next = Node(2)
    head.next.next = Node(3)
    head.next.next.next = Node(4)
    head.next.next.next.next = Node(5)
    print("Linked List in the specified pattern:", end=" ")
    fun(head)
    print()  # New line
    # Deallocate memory (Python handles memory management automatically)
# This code is contributed by Shivam Gupta
````
````javascript
// Class definition for a Node in the linked list
class Node {
    constructor(data) {
        this.data = data; // Data contained in the node
        this.next = null; // Reference to the next node
    }
}
// Function to traverse and print the linked list in a specific pattern
function fun(start) {
    if (start === null) return; // Base case: If the node is null, return
    // Print the current node's data
    process.stdout.write(start.data + " ");
    // Recursive call for every second node
    if (start.next !== null && start.next.next !== null)
        fun(start.next.next);
    // Print the current node's data again
    process.stdout.write(start.data + " ");
}
// Example usage
function main() {
    // Creating the linked list: 1 -> 2 -> 3 -> 4 -> 5
    let head = new Node(1);
    head.next = new Node(2);
    head.next.next = new Node(3);
    head.next.next.next = new Node(4);
    head.next.next.next.next = new Node(5);
    // Print the linked list in the specified pattern
    process.stdout.write("Linked List in the specified pattern: ");
    fun(head);
    console.log(); // Print a new line at the end
}
// Call the main function to execute the example usage
main();
````
**(A)** 1 4 6 6 4 1
**(B)** 1 3 5 5 3 1
**(C)** 1 2 3 5
**(D)** 1 3 5 5 2 3 1
> **Answer: (B)**
> **Explanation:** The function prints the data of the current node and then recursively calls itself with the second next node (i.e., start->next->next).
> So, it prints the data of every alternate node of the linked list i.e 1 3 5, and then, since the next->next of 5 is null, it returns and prints the data of the current node, so it then prints 5 3 1.
> Therefore, for the given linked list 1->2->3->4->5->6, the function would print 1 3 5 5 3 1.
**Q9.** The following C function takes a simply-linked list as input argument. It modifies the list by moving the last element to the front of the list and returns the modified list. Some part of the code is left blank. Choose the correct alternative to replace the blank line. 
````cpp
#include <iostream>
// Define the Node structure
struct Node {
    int value;
    Node* next;
};
// Function to move the last element to the front of the
// linked list
Node* move_to_front(Node* head)
{
    // Check if the list is empty or has only one element
    if (head == nullptr || head->next == nullptr) {
        return head;
    }
    Node *p, *q;
    q = nullptr; // q is used to keep track of the previous
                 // node
    p = head; // p is used to traverse the linked list
    // Traverse the linked list until the last element is
    // reached
    while (p->next != nullptr) {
        q = p;
        p = p->next;
    }
    // Move the last element to the front
    q->next = nullptr; // Set the next of the second-to-last
                       // node to null
    p->next = head; // Set the next of the last node to the
                    // original head
    head = p; // Update the head to the last node
    // Additional processing or printing can be done here if
    // needed
    return head;
}
int main()
{
    // Example usage of the move_to_front function
    Node* head
        = new Node{ 1,
                    new Node{ 2, new Node{ 3, nullptr } } };
    // Display the original linked list
    std::cout << "Original Linked List: ";
    Node* current = head;
    while (current != nullptr) {
        std::cout << current->value << " ";
        current = current->next;
    }
    std::cout << std::endl;
    // Call the move_to_front function
    head = move_to_front(head);
    // Display the modified linked list
    std::cout << "Modified Linked List: ";
    current = head;
    while (current != nullptr) {
        std::cout << current->value << " ";
        current = current->next;
    }
    std::cout << std::endl;
    // Clean up the memory (deallocation) - you may need to
    // implement a proper deallocation function
    while (head != nullptr) {
        Node* temp = head;
        head = head->next;
        delete temp;
    }
    return 0;
}
````
````c
#include <stdio.h>
#include <stdlib.h>
// Define the Node structure
struct Node {
    int value;
    struct Node* next;
};
// Function to move the last element to the front of the
// linked list
struct Node* move_to_front(struct Node* head)
{
    // Check if the list is empty or has only one element
    if (head == NULL || head->next == NULL) {
        return head;
    }
    struct Node *p, *q;
    q = NULL; // q is used to keep track of the previous
              // node
    p = head; // p is used to traverse the linked list
    // Traverse the linked list until the last element is
    // reached
    while (p->next != NULL) {
        q = p;
        p = p->next;
    }
    // Move the last element to the front
    q->next = NULL; // Set the next of the second-to-last
                    // node to null
    p->next = head; // Set the next of the last node to the
                    // original head
    head = p; // Update the head to the last node
    // Additional processing or printing can be done here if
    // needed
    return head;
}
int main()
{
    // Example usage of the move_to_front function
    struct Node* head = malloc(sizeof(struct Node));
    head->value = 1;
    head->next = malloc(sizeof(struct Node));
    head->next->value = 2;
    head->next->next = malloc(sizeof(struct Node));
    head->next->next->value = 3;
    head->next->next->next = NULL;
    // Display the original linked list
    printf("Original Linked List: ");
    struct Node* current = head;
    while (current != NULL) {
        printf("%d ", current->value);
        current = current->next;
    }
    printf("\n");
    // Call the move_to_front function
    head = move_to_front(head);
    // Display the modified linked list
    printf("Modified Linked List: ");
    current = head;
    while (current != NULL) {
        printf("%d ", current->value);
        current = current->next;
    }
    printf("\n");
    // Clean up the memory (deallocation) - you may need to
    // implement a proper deallocation function
    while (head != NULL) {
        struct Node* temp = head;
        head = head->next;
        free(temp);
    }
    return 0;
}
````
````java
public class Main {
    // Define the Node structure
    static class Node {
        int value;
        Node next;
        Node(int value)
        {
            this.value = value;
            this.next = null;
        }
    }
    // Function to move the last element to the front of the
    // linked list
    static Node moveToFront(Node head)
    {
        // Check if the list is empty or has only one
        // element
        if (head == null || head.next == null) {
            return head;
        }
        Node p
            = head; // p is used to traverse the linked list
        Node q = null; // q is used to keep track of the
                       // previous node
        // Traverse the linked list until the last element
        // is reached
        while (p.next != null) {
            q = p;
            p = p.next;
        }
        // Move the last element to the front
        q.next = null; // Set the next of the second-to-last
                       // node to null
        p.next = head; // Set the next of the last node to
                       // the original head
        head = p; // Update the head to the last node
        return head;
    }
    public static void main(String[] args)
    {
        // Example usage of the moveToFront function
        Node head = new Node(1);
        head.next = new Node(2);
        head.next.next = new Node(3);
        // Display the original linked list
        System.out.print("Original Linked List: ");
        Node current = head;
        while (current != null) {
            System.out.print(current.value + " ");
            current = current.next;
        }
        System.out.println();
        // Call the moveToFront function
        head = moveToFront(head);
        // Display the modified linked list
        System.out.print("Modified Linked List: ");
        current = head;
        while (current != null) {
            System.out.print(current.value + " ");
            current = current.next;
        }
        System.out.println();
    }
}
````
````python3
class Node:
    def __init__(self, value):
        self.value = value
        self.next = None
def moveToFront(head):
    # Check if the list is empty or has only one element
    if head is None or head.next is None:
        return head
    p = head   # p is used to traverse the linked list
    q = None   # q is used to keep track of the previous node
    # Traverse the linked list until the last element is reached
    while p.next is not None:
        q = p
        p = p.next
    # Move the last element to the front
    q.next = None       # Set the next of the second-to-last node to None
    p.next = head      # Set the next of the last node to the original head
    head = p            # Update the head to the last node
    return head
# Example usage of the moveToFront function
head = Node(1)
head.next = Node(2)
head.next.next = Node(3)
# Display the original linked list
print("Original Linked List:", end=" ")
current = head
while current is not None:
    print(current.value, end=" ")
    current = current.next
print()
# Call the moveToFront function
head = moveToFront(head)
# Display the modified linked list
print("Modified Linked List:", end=" ")
current = head
while current is not None:
    print(current.value, end=" ")
    current = current.next
print()
````
````javascript
class Node {
    constructor(value) {
        this.value = value;
        this.next = null;
    }
}
function moveToFront(head) {
    // Check if the list is empty or has only one element
    if (head === null || head.next === null) {
        return head;
    }
    let p = head;   // p is used to traverse the linked list
    let q = null;   // q is used to keep track of the previous node
    // Traverse the linked list until the last element is reached
    while (p.next !== null) {
        q = p;
        p = p.next;
    }
    // Move the last element to the front
    q.next = null;     // Set the next of the second-to-last node to null
    p.next = head;    // Set the next of the last node to the original head
    head = p;          // Update the head to the last node
    return head;
}
// Example usage of the moveToFront function
let head = new Node(1);
head.next = new Node(2);
head.next.next = new Node(3);
// Display the original linked list
process.stdout.write("Original Linked List: ");
let current = head;
while (current !== null) {
    process.stdout.write(current.value + " ");
    current = current.next;
}
console.log();
// Call the moveToFront function
head = moveToFront(head);
// Display the modified linked list
process.stdout.write("Modified Linked List: ");
current = head;
while (current !== null) {
    process.stdout.write(current.value + " ");
    current = current.next;
}
console.log();
// This code is contributed by Shivam Gupta
````
**(A)** q = NULL; p->next = head; head = p;
**(B)** q->next = NULL; head = p; p->next = head;
**(C)** head = p; p->next = q; q->next = NULL;
**(D)** q->next = NULL; p->next = head; head = p;
> **Answer: (D)**
> **Explanation:** To move the last element to the front of the list, we need to do the following steps:
>
> 1. Make the second last node as the last node (i.e., set its next pointer to NULL).
> 2. Set the next pointer of the current last node (which is now the second last node) to the original head node.
> 3. Make the current last node as the new head node.
**Q10.** The following function takes a single-linked list of integers as a parameter and rearranges the elements of the list. The function is called with the list containing the integers 1, 2, 3, 4, 5, 6, 7 in the given order. What will be the contents of the list after the function completes execution? 
````cpp
class Node {
public:
    int value;
    Node* next;
    Node(int value) {
        this->value = value;
        this->next = nullptr;
    }
};
void rearrange(Node* list) {
    Node* p;
    Node* q;
    int temp;
    if (list == nullptr || list->next == nullptr) {
        return;
    }
    p = list;
    q = list->next;
    while (q != nullptr) {
        temp = p->value;
        p->value = q->value;
        q->value = temp;
        p = q->next;
        q = p != nullptr ? p->next : nullptr;
    }
}
````
````java
class Node {
    int value;
    Node next;
}
void rearrange(Node list) {
    Node p, q;
    int temp;
    if (list == null || list.next == null) {
        return;
    }
    p = list;
    q = list.next;
    while (q != null) {
        temp = p.value;
        p.value = q.value;
        q.value = temp;
        p = q.next;
        q = p != null ? p.next : null;
    }
}
````
````javascript
class Node {
    constructor(value) {
        this.value = value;
        this.next = null;
    }
}
function rearrange(list) {
    // Initialize pointers p and q
    let p, q;
    let temp;
    // If the list is empty or has only one node, do nothing
    if (list === null || list.next === null) {
        return;
    }
    p = list;
    q = list.next;
    // Traverse the list in pairs
    while (q !== null) {
        // Swap the values of the nodes
        temp = p.value;
        p.value = q.value;
        q.value = temp;
        // Move to the next pair of nodes
        p = q.next;
        q = (p !== null) ? p.next : null;
    }
}
````
**(A)**1,2,3,4,5,6,7
**(B)**2,1,4,3,6,5,7
**(C)**1,3,2,5,4,7,6
**(D)**2,3,4,5,6,7,1
> **Answer: (B)**
> **Explanation:** The function rearrange() exchanges data of every node with its next node. It starts exchanging data from the first node itself.
> For eg. 2,1,4,3,6,5,7
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dsa/linked-list-notes-for-gate-exam/#what-is-linked-list)

## GATE CS

- Subject: Data Structures & C Programming
- Topic: Linked List

> [!note] Related notes
>
> - [[1D, 2D and 3D Arrays]]
> - [[CATEGORY ARCHIVES DATA STRUCTURES]]
> - [[Data Types in C]]
> - [[Double Hashing]]
> - [[Enum, Struct & Union in C]]
> - [[Functions in C]]
> - [[I ntroduction to Trees]]
> - [[Introduction to Arrays]]
> - [[Introduction to C Programming]]
> - [[Introduction to Graphs]]

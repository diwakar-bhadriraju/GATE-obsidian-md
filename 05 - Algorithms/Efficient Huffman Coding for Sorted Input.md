---
title: "Efficient Huffman Coding for Sorted Input | Greedy Algo-4"
subject: "Algorithms"
topic: "Greedy Techniques"
source: "https://www.geeksforgeeks.org/dsa/efficient-huffman-coding-for-sorted-input-greedy-algo-4/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Algorithms/Greedy Techniques"
tags:
  - gate/cs
  - subject/algorithms
  - topic/greedy-techniques
---


> [!abstract] Efficient Huffman Coding for Sorted Input | Greedy Algo-4
> 
> **Subject:** `Algorithms` &nbsp;|&nbsp; **Topic:** `Greedy Techniques`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dsa/efficient-huffman-coding-for-sorted-input-greedy-algo-4/)

---

# Efficient Huffman Coding for Sorted Input | Greedy Algo-4

We recommend to read following post as a prerequisite for this.
[Greedy Algorithms | Set 3 (Huffman Coding)](https://www.geeksforgeeks.org/dsa/huffman-coding-greedy-algo-3/)
Time complexity of the algorithm discussed in above post is O(nLogn). If we know that the given array is sorted (by non-decreasing order of frequency), we can generate Huffman codes in O(n) time. Following is a O(n) algorithm for sorted input.
**1.** Create two empty queues.
**2.** Create a leaf node for each unique character and Enqueue it to the first queue in non-decreasing order of frequency. Initially second queue is empty.
**3.** Dequeue two nodes with the minimum frequency by examining the front of both queues. Repeat the following steps two times 
        1. If second queue is empty, dequeue from first queue. 
        2. If first queue is empty, dequeue from second queue. 
        3. Else, compare the front of two queues and dequeue the minimum. 
**4.** Create a new internal node with frequency equal to the sum of the two nodes frequencies. Make the first Dequeued node as its left child and the second Dequeued node as right child. Enqueue this node to second queue.
**5.** Repeat steps#3 and #4 while there is more than one node in the queues. The remaining node is the root node and the tree is complete. 
C++14
````cpp14
// Clean c++ stl code to generate huffman codes if the array
// is sorted in non-decreasing order
#include <bits/stdc++.h>
using namespace std;
// Node structure for creating a binary tree
struct Node {
    char ch;
    int freq;
    Node* left;
    Node* right;
    Node(char c, int f, Node* l = nullptr,
         Node* r = nullptr)
        : ch(c)
        , freq(f)
        , left(l)
        , right(r){};
};
// Find the min freq node between q1 and q2
Node* minNode(queue<Node*>& q1, queue<Node*>& q2)
{
    Node* temp;
    if (q1.empty()) {
        temp = q2.front();
        q2.pop();
        return temp;
    }
    if (q2.empty()) {
        temp = q1.front();
        q1.pop();
        return temp;
    }
    if (q1.front()->freq < q2.front()->freq) {
        temp = q1.front();
        q1.pop();
        return temp;
    }
    else {
        temp = q2.front();
        q2.pop();
        return temp;
    }
}
// Function to print the generated huffman codes
void printHuffmanCodes(Node* root, string str = "")
{
    if (!root)
        return;
    if (root->ch != '$') {
        cout << root->ch << ": " << str << '\n';
        return;
    }
    printHuffmanCodes(root->left, str + "0");
    printHuffmanCodes(root->right, str + "1");
    return;
}
// Function to generate huffman codes
void generateHuffmanCode(vector<pair<char, int> > v)
{
    if (!v.size())
        return;
    queue<Node*> q1;
    queue<Node*> q2;
    for (auto it = v.begin(); it != v.end(); ++it)
        q1.push(new Node(it->first, it->second));
    while (!q1.empty() or q2.size() > 1) {
        Node* l = minNode(q1, q2);
        Node* r = minNode(q1, q2);
        Node* node = new Node('$', l->freq + r->freq, l, r);
        q2.push(node);
    }
    printHuffmanCodes(q2.front());
    return;
}
int main()
{
    vector<pair<char, int> > v
        = { { 'a' , 5 },  { 'b' , 9 },  { 'c' , 12 },
            { 'd' , 13 }, { 'e' , 16 }, { 'f' , 45 } };
    generateHuffmanCode(v);
    return 0;
}
````
````cpp
// C++ Program for Efficient Huffman Coding for Sorted input
#include <bits/stdc++.h>
using namespace std;
// This constant can be avoided by explicitly
// calculating height of Huffman Tree
#define MAX_TREE_HT 100
// A node of huffman tree
class QueueNode {
public:
    char data;
    unsigned freq;
    QueueNode *left, *right;
};
// Structure for Queue: collection
// of Huffman Tree nodes (or QueueNodes)
class Queue {
public:
    int front, rear;
    int capacity;
    QueueNode** array;
};
// A utility function to create a new Queuenode
QueueNode* newNode(char data, unsigned freq)
{
    QueueNode* temp = new QueueNode[(sizeof(QueueNode))];
    temp->left = temp->right = NULL;
    temp->data = data;
    temp->freq = freq;
    return temp;
}
// A utility function to create a Queue of given capacity
Queue* createQueue(int capacity)
{
    Queue* queue = new Queue[(sizeof(Queue))];
    queue->front = queue->rear = -1;
    queue->capacity = capacity;
    queue->array = new QueueNode*[(queue->capacity
                                   * sizeof(QueueNode*))];
    return queue;
}
// A utility function to check if size of given queue is 1
int isSizeOne(Queue* queue)
{
    return queue->front == queue->rear
           && queue->front != -1;
}
// A utility function to check if given queue is empty
int isEmpty(Queue* queue) { return queue->front == -1; }
// A utility function to check if given queue is full
int isFull(Queue* queue)
{
    return queue->rear == queue->capacity - 1;
}
// A utility function to add an item to queue
void enQueue(Queue* queue, QueueNode* item)
{
    if (isFull(queue))
        return;
    queue->array[++queue->rear] = item;
    if (queue->front == -1)
        ++queue->front;
}
// A utility function to remove an item from queue
QueueNode* deQueue(Queue* queue)
{
    if (isEmpty(queue))
        return NULL;
    QueueNode* temp = queue->array[queue->front];
    if (queue->front
        == queue
               ->rear) // If there is only one item in queue
        queue->front = queue->rear = -1;
    else
        ++queue->front;
    return temp;
}
// A utility function to get form of queue
QueueNode* getFront(Queue* queue)
{
    if (isEmpty(queue))
        return NULL;
    return queue->array[queue->front];
}
/* A function to get minimum item from two queues */
QueueNode* findMin(Queue* firstQueue, Queue* secondQueue)
{
    // Step 3.a: If first queue is empty, dequeue from
    // second queue
    if (isEmpty(firstQueue))
        return deQueue(secondQueue);
    // Step 3.b: If second queue is empty, dequeue from
    // first queue
    if (isEmpty(secondQueue))
        return deQueue(firstQueue);
    // Step 3.c: Else, compare the front of two queues and
    // dequeue minimum
    if (getFront(firstQueue)->freq
        < getFront(secondQueue)->freq)
        return deQueue(firstQueue);
    return deQueue(secondQueue);
}
// Utility function to check if this node is leaf
int isLeaf(QueueNode* root)
{
    return !(root->left) && !(root->right);
}
// A utility function to print an array of size n
void printArr(int arr[], int n)
{
    int i;
    for (i = 0; i < n; ++i)
        cout << arr[i];
    cout << endl;
}
// The main function that builds Huffman tree
QueueNode* buildHuffmanTree(char data[], int freq[],
                            int size)
{
    QueueNode *left, *right, *top;
    // Step 1: Create two empty queues
    Queue* firstQueue = createQueue(size);
    Queue* secondQueue = createQueue(size);
    // Step 2:Create a leaf node for each unique character
    // and Enqueue it to the first queue in non-decreasing
    // order of frequency. Initially second queue is empty
    for (int i = 0; i < size; ++i)
        enQueue(firstQueue, newNode(data[i], freq[i]));
    // Run while Queues contain more than one node. Finally,
    // first queue will be empty and second queue will
    // contain only one node
    while (
        !(isEmpty(firstQueue) && isSizeOne(secondQueue))) {
        // Step 3: Dequeue two nodes with the minimum
        // frequency by examining the front of both queues
        left = findMin(firstQueue, secondQueue);
        right = findMin(firstQueue, secondQueue);
        // Step 4: Create a new internal node with frequency
        // equal to the sum of the two nodes frequencies.
        // Enqueue this node to second queue.
        top = newNode('$', left->freq + right->freq);
        top->left = left;
        top->right = right;
        enQueue(secondQueue, top);
    }
    return deQueue(secondQueue);
}
// Prints huffman codes from the root of Huffman Tree. It
// uses arr[] to store codes
void printCodes(QueueNode* root, int arr[], int top)
{
    // Assign 0 to left edge and recur
    if (root->left) {
        arr[top] = 0;
        printCodes(root->left, arr, top + 1);
    }
    // Assign 1 to right edge and recur
    if (root->right) {
        arr[top] = 1;
        printCodes(root->right, arr, top + 1);
    }
    // If this is a leaf node, then it contains one of the
    // input characters, print the character and its code
    // from arr[]
    if (isLeaf(root)) {
        cout << root->data << ": ";
        printArr(arr, top);
    }
}
// The main function that builds a Huffman Tree and print
// codes by traversing the built Huffman Tree
void HuffmanCodes(char data[], int freq[], int size)
{
    // Construct Huffman Tree
    QueueNode* root = buildHuffmanTree(data, freq, size);
    // Print Huffman codes using the Huffman tree built
    // above
    int arr[MAX_TREE_HT], top = 0;
    printCodes(root, arr, top);
}
// Driver code
int main()
{
    char arr[] = { 'a', 'b', 'c', 'd', 'e', 'f' };
    int freq[] = { 5, 9, 12, 13, 16, 45 };
    int size = sizeof(arr) / sizeof(arr[0]);
    HuffmanCodes(arr, freq, size);
    return 0;
}
// This code is contributed by rathbhupendra
````
````cpp
// C Program for Efficient Huffman Coding for Sorted input
#include <stdio.h>
#include <stdlib.h>
// This constant can be avoided by explicitly calculating
// height of Huffman Tree
#define MAX_TREE_HT 100
// A node of huffman tree
struct QueueNode {
    char data;
    unsigned freq;
    struct QueueNode *left, *right;
};
// Structure for Queue: collection of Huffman Tree nodes (or
// QueueNodes)
struct Queue {
    int front, rear;
    int capacity;
    struct QueueNode** array;
};
// A utility function to create a new Queuenode
struct QueueNode* newNode(char data, unsigned freq)
{
    struct QueueNode* temp = (struct QueueNode*)malloc(
        sizeof(struct QueueNode));
    temp->left = temp->right = NULL;
    temp->data = data;
    temp->freq = freq;
    return temp;
}
// A utility function to create a Queue of given capacity
struct Queue* createQueue(int capacity)
{
    struct Queue* queue
        = (struct Queue*)malloc(sizeof(struct Queue));
    queue->front = queue->rear = -1;
    queue->capacity = capacity;
    queue->array = (struct QueueNode**)malloc(
        queue->capacity * sizeof(struct QueueNode*));
    return queue;
}
// A utility function to check if size of given queue is 1
int isSizeOne(struct Queue* queue)
{
    return queue->front == queue->rear
           && queue->front != -1;
}
// A utility function to check if given queue is empty
int isEmpty(struct Queue* queue)
{
    return queue->front == -1;
}
// A utility function to check if given queue is full
int isFull(struct Queue* queue)
{
    return queue->rear == queue->capacity - 1;
}
// A utility function to add an item to queue
void enQueue(struct Queue* queue, struct QueueNode* item)
{
    if (isFull(queue))
        return;
    queue->array[++queue->rear] = item;
    if (queue->front == -1)
        ++queue->front;
}
// A utility function to remove an item from queue
struct QueueNode* deQueue(struct Queue* queue)
{
    if (isEmpty(queue))
        return NULL;
    struct QueueNode* temp = queue->array[queue->front];
    if (queue->front
        == queue
               ->rear) // If there is only one item in queue
        queue->front = queue->rear = -1;
    else
        ++queue->front;
    return temp;
}
// A utility function to get form of queue
struct QueueNode* getFront(struct Queue* queue)
{
    if (isEmpty(queue))
        return NULL;
    return queue->array[queue->front];
}
/* A function to get minimum item from two queues */
struct QueueNode* findMin(struct Queue* firstQueue,
                          struct Queue* secondQueue)
{
    // Step 3.a: If first queue is empty, dequeue from
    // second queue
    if (isEmpty(firstQueue))
        return deQueue(secondQueue);
    // Step 3.b: If second queue is empty, dequeue from
    // first queue
    if (isEmpty(secondQueue))
        return deQueue(firstQueue);
    // Step 3.c:  Else, compare the front of two queues and
    // dequeue minimum
    if (getFront(firstQueue)->freq
        < getFront(secondQueue)->freq)
        return deQueue(firstQueue);
    return deQueue(secondQueue);
}
// Utility function to check if this node is leaf
int isLeaf(struct QueueNode* root)
{
    return !(root->left) && !(root->right);
}
// A utility function to print an array of size n
void printArr(int arr[], int n)
{
    int i;
    for (i = 0; i < n; ++i)
        printf("%d", arr[i]);
    printf("\n");
}
// The main function that builds Huffman tree
struct QueueNode* buildHuffmanTree(char data[], int freq[],
                                   int size)
{
    struct QueueNode *left, *right, *top;
    // Step 1: Create two empty queues
    struct Queue* firstQueue = createQueue(size);
    struct Queue* secondQueue = createQueue(size);
    // Step 2:Create a leaf node for each unique character
    // and Enqueue it to the first queue in non-decreasing
    // order of frequency. Initially second queue is empty
    for (int i = 0; i < size; ++i)
        enQueue(firstQueue, newNode(data[i], freq[i]));
    // Run while Queues contain more than one node. Finally,
    // first queue will be empty and second queue will
    // contain only one node
    while (
        !(isEmpty(firstQueue) && isSizeOne(secondQueue))) {
        // Step 3: Dequeue two nodes with the minimum
        // frequency by examining the front of both queues
        left = findMin(firstQueue, secondQueue);
        right = findMin(firstQueue, secondQueue);
        // Step 4: Create a new internal node with frequency
        // equal to the sum of the two nodes frequencies.
        // Enqueue this node to second queue.
        top = newNode('$', left->freq + right->freq);
        top->left = left;
        top->right = right;
        enQueue(secondQueue, top);
    }
    return deQueue(secondQueue);
}
// Prints huffman codes from the root of Huffman Tree.  It
// uses arr[] to store codes
void printCodes(struct QueueNode* root, int arr[], int top)
{
    // Assign 0 to left edge and recur
    if (root->left) {
        arr[top] = 0;
        printCodes(root->left, arr, top + 1);
    }
    // Assign 1 to right edge and recur
    if (root->right) {
        arr[top] = 1;
        printCodes(root->right, arr, top + 1);
    }
    // If this is a leaf node, then it contains one of the
    // input characters, print the character and its code
    // from arr[]
    if (isLeaf(root)) {
        printf("%c: ", root->data);
        printArr(arr, top);
    }
}
// The main function that builds a Huffman Tree and print
// codes by traversing the built Huffman Tree
void HuffmanCodes(char data[], int freq[], int size)
{
    //  Construct Huffman Tree
    struct QueueNode* root
        = buildHuffmanTree(data, freq, size);
    // Print Huffman codes using the Huffman tree built
    // above
    int arr[MAX_TREE_HT], top = 0;
    printCodes(root, arr, top);
}
// Driver program to test above functions
int main()
{
    char arr[] = { 'a', 'b', 'c', 'd', 'e', 'f' };
    int freq[] = { 5, 9, 12, 13, 16, 45 };
    int size = sizeof(arr) / sizeof(arr[0]);
    HuffmanCodes(arr, freq, size);
    return 0;
}
````
````java
//// C++ Program for Efficient Huffman Coding for Sorted input //
import java.util.PriorityQueue;
import java.util.HashMap;
// Node structure for creating a binary tree //
class Node {
    char ch;
    int freq;
    Node left;
    Node right;
    Node(char c, int f) {
        ch = c;
        freq = f;
        left = null;
        right = null;
    }
}
public class Main {
    // Function to print the generated Huffman codes
    static void printHuffmanCodes(Node root, String str) {
        if (root == null)
            return;
        if (root.ch != '$') {
            System.out.println(root.ch + ": " + str);
            return;
        }
        printHuffmanCodes(root.left, str + "0");
        printHuffmanCodes(root.right, str + "1");
    }
    // Function to generate Huffman codes
    static void generateHuffmanCode(HashMap<Character, Integer> charFreq) {
        if (charFreq.isEmpty())
            return;
        PriorityQueue<Node> pq = new PriorityQueue<>((a, b) -> a.freq - b.freq);
        for (char c : charFreq.keySet()) {
            pq.add(new Node(c, charFreq.get(c)));
        }
        while (pq.size() > 1) {
            Node left = pq.poll();
            Node right = pq.poll();
            Node node = new Node('$', left.freq + right.freq);
            node.left = left;
            node.right = right;
            pq.add(node);
        }
        printHuffmanCodes(pq.poll(), "");
    }
    public static void main(String[] args) {
        HashMap<Character, Integer> charFreq = new HashMap<>();
        charFreq.put('a', 5);
        charFreq.put('b', 9);
        charFreq.put('c', 12);
        charFreq.put('d', 13);
        charFreq.put('e', 16);
        charFreq.put('f', 45);
        generateHuffmanCode(charFreq);
    }
}
````
````python3
# Python3 program for Efficient Huffman Coding
# for Sorted input
# Class for the nodes of the Huffman tree
class QueueNode:
    def __init__(self, data = None, freq = None,
                 left = None, right = None):
        self.data = data
        self.freq = freq
        self.left = left
        self.right = right
    # Function to check if the following
    # node is a leaf node
    def isLeaf(self):
        return (self.left == None and
                self.right == None)
# Class for the two Queues
class Queue:
    def __init__(self):
        self.queue = []
    # Function for checking if the
    # queue has only 1 node
    def isSizeOne(self):
        return len(self.queue) == 1
    # Function for checking if
    # the queue is empty
    def isEmpty(self):
        return self.queue == []
    # Function to add item to the queue
    def enqueue(self, x):
        self.queue.append(x)
    # Function to remove item from the queue
    def dequeue(self):
        return self.queue.pop(0)
# Function to get minimum item from two queues
def findMin(firstQueue, secondQueue):
    # Step 3.1: If second queue is empty,
    # dequeue from first queue
    if secondQueue.isEmpty():
        return firstQueue.dequeue()
    # Step 3.2: If first queue is empty,
    # dequeue from second queue
    if firstQueue.isEmpty():
        return secondQueue.dequeue()
    # Step 3.3:  Else, compare the front of
    # two queues and dequeue minimum
    if (firstQueue.queue[0].freq <
        secondQueue.queue[0].freq):
        return firstQueue.dequeue()
    return secondQueue.dequeue()
# The main function that builds Huffman tree
def buildHuffmanTree(data, freq, size):
    # Step 1: Create two empty queues
    firstQueue = Queue()
    secondQueue = Queue()
    # Step 2: Create a leaf node for each unique
    # character and Enqueue it to the first queue
    # in non-decreasing order of frequency.
    # Initially second queue is empty.
    for i in range(size):
        firstQueue.enqueue(QueueNode(data[i], freq[i]))
    # Run while Queues contain more than one node.
    # Finally, first queue will be empty and
    # second queue will contain only one node
    while not (firstQueue.isEmpty() and
               secondQueue.isSizeOne()):
        # Step 3: Dequeue two nodes with the minimum
        # frequency by examining the front of both queues
        left = findMin(firstQueue, secondQueue)
        right = findMin(firstQueue, secondQueue)
        # Step 4: Create a new internal node with
        # frequency equal to the sum of the two
        # nodes frequencies. Enqueue this node
        # to second queue.
        top = QueueNode("$", left.freq + right.freq,
                        left, right)
        secondQueue.enqueue(top)
    return secondQueue.dequeue()
# Prints huffman codes from the root of
# Huffman tree. It uses arr[] to store codes
def printCodes(root, arr):
    # Assign 0 to left edge and recur
    if root.left:
        arr.append(0)
        printCodes(root.left, arr)
        arr.pop(-1)
    # Assign 1 to right edge and recur
    if root.right:
        arr.append(1)
        printCodes(root.right, arr)
        arr.pop(-1)
    # If this is a leaf node, then it contains
    # one of the input characters, print the
    # character and its code from arr[]
    if root.isLeaf():
        print(f"{root.data}: ", end = "")
        for i in arr:
            print(i, end = "")
        print()
# The main function that builds a Huffman
# tree and print codes by traversing the
# built Huffman tree
def HuffmanCodes(data, freq, size):
    # Construct Huffman Tree
    root = buildHuffmanTree(data, freq, size)
    # Print Huffman codes using the Huffman
    # tree built above
    arr = []
    printCodes(root, arr)
# Driver code
arr = ["a", "b", "c", "d", "e", "f"]
freq = [5, 9, 12, 13, 16, 45]
size = len(arr)
HuffmanCodes(arr, freq, size)
# This code is contributed by Kevin Joshi
````
````csharp
// Clean c++ stl code to generate huffman codes if the array
// is sorted in non-decreasing order
using System;
using System.Collections.Generic;
// Node structure for creating a binary tree
public class Node {
    public char Ch
    {
        get;
        set;
    }
    public int Freq
    {
        get;
        set;
    }
    public Node Left
    {
        get;
        set;
    }
    public Node Right
    {
        get;
        set;
    }
    public Node(char c, int f, Node l = null, Node r = null)
    {
        Ch = c;
        Freq = f;
        Left = l;
        Right = r;
    }
}
class Program {
    // Find the min freq node between q1 and q2
    static Node MinNode(Queue<Node> q1, Queue<Node> q2)
    {
        Node temp;
        if (q1.Count == 0) {
            temp = q2.Dequeue();
            return temp;
        }
        if (q2.Count == 0) {
            temp = q1.Dequeue();
            return temp;
        }
        if (q1.Peek().Freq < q2.Peek().Freq) {
            temp = q1.Dequeue();
            return temp;
        }
        else {
            temp = q2.Dequeue();
            return temp;
        }
    }
    // Function to print the generated huffman codes
    static void PrintHuffmanCodes(Node root,
                                  string str = "")
    {
        if (root == null)
            return;
        if (root.Ch != '$') {
            Console.WriteLine(root.Ch + ": " + str);
            return;
        }
        PrintHuffmanCodes(root.Left, str + "0");
        PrintHuffmanCodes(root.Right, str + "1");
    }
    // Function to generate huffman codes
    static void
    GenerateHuffmanCode(List<Tuple<char, int> > v)
    {
        if (v.Count == 0)
            return;
        Queue<Node> q1 = new Queue<Node>();
        Queue<Node> q2 = new Queue<Node>();
        foreach(var tuple in v)
        {
            q1.Enqueue(new Node(tuple.Item1, tuple.Item2));
        }
        while (q1.Count > 0 || q2.Count > 1) {
            Node l = MinNode(q1, q2);
            Node r = MinNode(q1, q2);
            Node node
                = new Node('$', l.Freq + r.Freq, l, r);
            q2.Enqueue(node);
        }
        PrintHuffmanCodes(q2.Peek());
    }
    static void Main(string[] args)
    {
        List<Tuple<char, int> > v
            = new List<Tuple<char, int> >{
                  Tuple.Create('a', 5),
                  Tuple.Create('b', 9),
                  Tuple.Create('c', 12),
                  Tuple.Create('d', 13),
                  Tuple.Create('e', 16),
                  Tuple.Create('f', 45)
              };
        GenerateHuffmanCode(v);
    }
}
````
````javascript
// JavaScript program for the above approach
// Class for the nodes of the Huffman tree
class QueueNode {
  constructor(data = null, freq = null, left = null, right = null) {
    this.data = data;
    this.freq = freq;
    this.left = left;
    this.right = right;
  }
    // Function to check if the following
    // node is a leaf node
  isLeaf() {
    return (this.left == null && this.right == null);
  }
}
// Class for the two Queues
class Queue {
  constructor() {
    this.queue = [];
  }
   // Function for checking if the
   // queue has only 1 node
  isSizeOne() {
    return this.queue.length == 1;
  }
   // Function for checking if
   // the queue is empty
  isEmpty() {
    return this.queue.length == 0;
  }
  // Function to add item to the queue
  enqueue(x) {
    this.queue.push(x);
  }
   // Function to remove item from the queue
  dequeue() {
    return this.queue.shift();
  }
}
// Function to get minimum item from two queues
function findMin(firstQueue, secondQueue) {
    // Step 3.1: If second queue is empty,
   // dequeue from first queue
  if (secondQueue.isEmpty()) {
    return firstQueue.dequeue();
  }
   // Step 3.2: If first queue is empty,
  // dequeue from second queue
  if (firstQueue.isEmpty()) {
    return secondQueue.dequeue();
  }
    // Step 3.3:  Else, compare the front of
   // two queues and dequeue minimum
  if (firstQueue.queue[0].freq < secondQueue.queue[0].freq) {
    return firstQueue.dequeue();
  }
  return secondQueue.dequeue();
}
// The main function that builds Huffman tree
function buildHuffmanTree(data, freq, size) {
  // Step 1: Create two empty queues
  let firstQueue = new Queue();
  let secondQueue = new Queue();
   // Step 2: Create a leaf node for each unique
   // character and Enqueue it to the first queue
   // in non-decreasing order of frequency.
   // Initially second queue is empty.
  for (let i = 0; i < size; i++) {
    firstQueue.enqueue(new QueueNode(data[i], freq[i]));
  }
  // Run while Queues contain more than one node.
  // Finally, first queue will be empty and
  // second queue will contain only one node
  while (!(firstQueue.isEmpty() && secondQueue.isSizeOne())) {
    // Step 3: Dequeue two nodes with the minimum
    // frequency by examining the front of both queues
    let left = findMin(firstQueue, secondQueue);
    let right = findMin(firstQueue, secondQueue);
    // Step 4: Create a new internal node with
    // frequency equal to the sum of the two
    // nodes frequencies. Enqueue this node
    // to second queue.
    let top = new QueueNode("$", left.freq + right.freq, left, right);
    secondQueue.enqueue(top);
  }
  return secondQueue.dequeue();
}
// Prints huffman codes from the root of
// Huffman tree. It uses arr[] to store codes
function printCodes(root, arr) {
  // Assign 0 to left edge and recur
  if (root.left) {
    arr.push(0);
    printCodes(root.left, arr);
    arr.pop();
  }
  // Assign 1 to right edge and recur
  if (root.right) {
    arr.push(1);
    printCodes(root.right, arr);
    arr.pop();
  }
   // If this is a leaf node, then it contains
  // one of the input characters, print the
  // character and its code from arr[]
  if (root.isLeaf()) {
    let output = root.data + ": ";
    for (let i = 0; i < arr.length; i++) {
      output += arr[i];
    }
    console.log(output);
  }
}
// The main function that builds a Huffman
// tree and print codes by traversing the
// built Huffman tree
function HuffmanCodes(data, freq, size) {
  // Construct Huffman Tree
  let root = buildHuffmanTree(data, freq, size);
  // Print Huffman codes using the Huffman
  // tree built above
  let arr = [];
  printCodes(root, arr);
}
// Driver code
let arr = ["a", "b", "c", "d", "e", "f"];
let freq = [5, 9, 12, 13, 16, 45];
let size = arr.length;
HuffmanCodes(arr, freq, size);
// This code is contributed by Prince Kumar
````
**Output:**
```
f: 0c: 100d: 101a: 1100b: 1101e: 111
```
**Time complexity:** O(n)
If the input is not sorted, it needs to be sorted first before it can be processed by the above algorithm. Sorting can be done using heap sort or merge-sort both of which run in Theta(nlogn). So, the overall time complexity becomes O(nlogn) for unsorted input. 
**Auxiliary Space:** O(n)
**Reference:** 
<https://en.wikipedia.org/wiki/Huffman_coding>
This article is compiled by Aashish Barnwal and reviewed by GeeksforGeeks team.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dsa/efficient-huffman-coding-for-sorted-input-greedy-algo-4/)

## GATE CS

- Subject: Algorithms
- Topic: Greedy Techniques

> [!note] Related notes
>
> - [[Dijkstra’s Algorithm for Adjacency List Representation]]
> - [[Fractional Knapsack Problem]]
> - [[Introduction to Greedy Algorithms]]
> - [[Optimal File Merge Patterns]]
> - [[Prim’s Minimum Spanning Tree]]
> - [[Prim’s MST for Adjacency List Representation]]
> - [[Applications of Depth First Search]]
> - [[Asymptotic Notations]]
> - [[Binary Search]]
> - [[Breadth First Traversal or BFS for a Graph]]

---
title: "Prim’s MST for Adjacency List Representation | Greedy Algo-6"
subject: "Algorithms"
topic: "Greedy Techniques"
source: "https://www.geeksforgeeks.org/dsa/prims-mst-for-adjacency-list-representation-greedy-algo-6/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Algorithms/Greedy Techniques"
tags:
  - gate/cs
  - subject/algorithms
  - topic/greedy-techniques
---


> [!abstract] Prim’s MST for Adjacency List Representation | Greedy Algo-6
> 
> **Subject:** `Algorithms` &nbsp;|&nbsp; **Topic:** `Greedy Techniques`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dsa/prims-mst-for-adjacency-list-representation-greedy-algo-6/)

---

# Prim’s MST for Adjacency List Representation | Greedy Algo-6

We recommend reading the following two posts as a prerequisite to this post.
1. [Greedy Algorithms | Set 5 (Prim’s Minimum Spanning Tree (MST))](https://www.geeksforgeeks.org/dsa/prims-minimum-spanning-tree-mst-greedy-algo-5/)
2. [Graph and its representations](https://www.geeksforgeeks.org/dsa/graph-and-its-representations/)
We have discussed [Prim's algorithm and its implementation for adjacency matrix representation of graphs](https://www.geeksforgeeks.org/dsa/prims-minimum-spanning-tree-mst-greedy-algo-5/). The time complexity for the matrix representation is O(V^2). In this post, O(ELogV) algorithm for adjacency list representation is discussed. 
As discussed in the previous post, in Prim's algorithm, two sets are maintained, one set contains list of vertices already included in MST, other set contains vertices not yet included. With adjacency list representation, all vertices of a graph can be traversed in O(V+E) time using [BFS](https://www.geeksforgeeks.org/dsa/breadth-first-search-or-bfs-for-a-graph/). The idea is to traverse all vertices of graph using [BFS](https://www.geeksforgeeks.org/dsa/breadth-first-search-or-bfs-for-a-graph/) and use a Min Heap to store the vertices not yet included in MST. Min Heap is used as a priority queue to get the minimum weight edge from the [cut](https://en.wikipedia.org/wiki/Cut_%28graph_theory%29). Min Heap is used as time complexity of operations like extracting minimum element and decreasing key value is O(LogV) in Min Heap.
> Following are the detailed steps. 
>
> 1. Create a Min Heap of size V where V is the number of vertices in the given graph. Every node of min heap contains vertex number and key value of the vertex.
> 2. Initialize Min Heap with first vertex as root (the key value assigned to first vertex is 0). The key value assigned to all other vertices is INF (infinite).
> 3. While Min Heap is not empty, do following 
>    1. Extract the min value node from Min Heap. Let the extracted vertex be u.
>    2. For every adjacent vertex v of u, check if v is in Min Heap (not yet included in MST). If v is in Min Heap and its key value is more than weight of u-v, then update the key value of v as weight of u-v.
Let us understand the above algorithm with the following example: 
![](assets/Fig-11-33e7a22705.jpg)
Initially, key value of first vertex is 0 and INF (infinite) for all other vertices. So vertex 0 is extracted from Min Heap and key values of vertices adjacent to 0 (1 and 7) are updated. Min Heap contains all vertices except vertex 0. 
The vertices in green color are the vertices included in MST. 
![](assets/MST1-bef9736692.jpg)
Since key value of vertex 1 is minimum among all nodes in Min Heap, it is extracted from Min Heap and key values of vertices adjacent to 1 are updated (Key is updated if the a vertex is in Min Heap and previous key value is greater than the weight of edge from 1 to the adjacent). Min Heap contains all vertices except vertex 0 and 1. 
![](assets/MST2-72e3f38b95.jpg)
Since key value of vertex 7 is minimum among all nodes in Min Heap, it is extracted from Min Heap and key values of vertices adjacent to 7 are updated (Key is updated if the a vertex is in Min Heap and previous key value is greater than the weight of edge from 7 to the adjacent). Min Heap contains all vertices except vertex 0, 1 and 7. 
![](assets/MST3-24bc9b0877.jpg)
Since key value of vertex 6 is minimum among all nodes in Min Heap, it is extracted from Min Heap and key values of vertices adjacent to 6 are updated (Key is updated if the a vertex is in Min Heap and previous key value is greater than the weight of edge from 6 to the adjacent). Min Heap contains all vertices except vertex 0, 1, 7 and 6. 
![](assets/MST4-2de47bcdd6.jpg)
The above steps are repeated for rest of the nodes in Min Heap till Min Heap becomes empty 
![](assets/MST5-f8961f5efc.jpg)
**Implementation:**
````cpp
// C / C++ program for Prim's MST for adjacency list
// representation of graph
#include <limits.h>
#include <stdio.h>
#include <stdlib.h>
// A structure to represent a node in adjacency list
struct AdjListNode {
    int dest;
    int weight;
    struct AdjListNode* next;
};
// A structure to represent an adjacency list
struct AdjList {
    struct AdjListNode*
        head; // pointer to head node of list
};
// A structure to represent a graph. A graph is an array of
// adjacency lists. Size of array will be V (number of
// vertices in graph)
struct Graph {
    int V;
    struct AdjList* array;
};
// A utility function to create a new adjacency list node
struct AdjListNode* newAdjListNode(int dest, int weight)
{
    struct AdjListNode* newNode
        = (struct AdjListNode*)malloc(
            sizeof(struct AdjListNode));
    newNode->dest = dest;
    newNode->weight = weight;
    newNode->next = NULL;
    return newNode;
}
// A utility function that creates a graph of V vertices
struct Graph* createGraph(int V)
{
    struct Graph* graph
        = (struct Graph*)malloc(sizeof(struct Graph));
    graph->V = V;
    // Create an array of adjacency lists.  Size of array
    // will be V
    graph->array = (struct AdjList*)malloc(
        V * sizeof(struct AdjList));
    // Initialize each adjacency list as empty by making
    // head as NULL
    for (int i = 0; i < V; ++i)
        graph->array[i].head = NULL;
    return graph;
}
// Adds an edge to an undirected graph
void addEdge(struct Graph* graph, int src, int dest,
             int weight)
{
    // Add an edge from src to dest.  A new node is added to
    // the adjacency list of src.  The node is added at the
    // beginning
    struct AdjListNode* newNode
        = newAdjListNode(dest, weight);
    newNode->next = graph->array[src].head;
    graph->array[src].head = newNode;
    // Since graph is undirected, add an edge from dest to
    // src also
    newNode = newAdjListNode(src, weight);
    newNode->next = graph->array[dest].head;
    graph->array[dest].head = newNode;
}
// Structure to represent a min heap node
struct MinHeapNode {
    int v;
    int key;
};
// Structure to represent a min heap
struct MinHeap {
    int size; // Number of heap nodes present currently
    int capacity; // Capacity of min heap
    int* pos; // This is needed for decreaseKey()
    struct MinHeapNode** array;
};
// A utility function to create a new Min Heap Node
struct MinHeapNode* newMinHeapNode(int v, int key)
{
    struct MinHeapNode* minHeapNode
        = (struct MinHeapNode*)malloc(
            sizeof(struct MinHeapNode));
    minHeapNode->v = v;
    minHeapNode->key = key;
    return minHeapNode;
}
// A utility function to create a Min Heap
struct MinHeap* createMinHeap(int capacity)
{
    struct MinHeap* minHeap
        = (struct MinHeap*)malloc(sizeof(struct MinHeap));
    minHeap->pos = (int*)malloc(capacity * sizeof(int));
    minHeap->size = 0;
    minHeap->capacity = capacity;
    minHeap->array = (struct MinHeapNode**)malloc(
        capacity * sizeof(struct MinHeapNode*));
    return minHeap;
}
// A utility function to swap two nodes of min heap. Needed
// for min heapify
void swapMinHeapNode(struct MinHeapNode** a,
                     struct MinHeapNode** b)
{
    struct MinHeapNode* t = *a;
    *a = *b;
    *b = t;
}
// A standard function to heapify at given idx
// This function also updates position of nodes when they
// are swapped. Position is needed for decreaseKey()
void minHeapify(struct MinHeap* minHeap, int idx)
{
    int smallest, left, right;
    smallest = idx;
    left = 2 * idx + 1;
    right = 2 * idx + 2;
    if (left < minHeap->size
        && minHeap->array[left]->key
               < minHeap->array[smallest]->key)
        smallest = left;
    if (right < minHeap->size
        && minHeap->array[right]->key
               < minHeap->array[smallest]->key)
        smallest = right;
    if (smallest != idx) {
        // The nodes to be swapped in min heap
        MinHeapNode* smallestNode
            = minHeap->array[smallest];
        MinHeapNode* idxNode = minHeap->array[idx];
        // Swap positions
        minHeap->pos[smallestNode->v] = idx;
        minHeap->pos[idxNode->v] = smallest;
        // Swap nodes
        swapMinHeapNode(&minHeap->array[smallest],
                        &minHeap->array[idx]);
        minHeapify(minHeap, smallest);
    }
}
// A utility function to check if the given minHeap is empty
// or not
int isEmpty(struct MinHeap* minHeap)
{
    return minHeap->size == 0;
}
// Standard function to extract minimum node from heap
struct MinHeapNode* extractMin(struct MinHeap* minHeap)
{
    if (isEmpty(minHeap))
        return NULL;
    // Store the root node
    struct MinHeapNode* root = minHeap->array[0];
    // Replace root node with last node
    struct MinHeapNode* lastNode
        = minHeap->array[minHeap->size - 1];
    minHeap->array[0] = lastNode;
    // Update position of last node
    minHeap->pos[root->v] = minHeap->size - 1;
    minHeap->pos[lastNode->v] = 0;
    // Reduce heap size and heapify root
    --minHeap->size;
    minHeapify(minHeap, 0);
    return root;
}
// Function to decrease key value of a given vertex v. This
// function uses pos[] of min heap to get the current index
// of node in min heap
void decreaseKey(struct MinHeap* minHeap, int v, int key)
{
    // Get the index of v in  heap array
    int i = minHeap->pos[v];
    // Get the node and update its key value
    minHeap->array[i]->key = key;
    // Travel up while the complete tree is not heapified.
    // This is a O(Logn) loop
    while (i
           && minHeap->array[i]->key
                  < minHeap->array[(i - 1) / 2]->key) {
        // Swap this node with its parent
        minHeap->pos[minHeap->array[i]->v] = (i - 1) / 2;
        minHeap->pos[minHeap->array[(i - 1) / 2]->v] = i;
        swapMinHeapNode(&minHeap->array[i],
                        &minHeap->array[(i - 1) / 2]);
        // move to parent index
        i = (i - 1) / 2;
    }
}
// A utility function to check if a given vertex
// 'v' is in min heap or not
bool isInMinHeap(struct MinHeap* minHeap, int v)
{
    if (minHeap->pos[v] < minHeap->size)
        return true;
    return false;
}
// A utility function used to print the constructed MST
void printArr(int arr[], int n)
{
    for (int i = 1; i < n; ++i)
        printf("%d - %d\n", arr[i], i);
}
// The main function that constructs Minimum Spanning Tree
// (MST) using Prim's algorithm
void PrimMST(struct Graph* graph)
{
    int V = graph->V; // Get the number of vertices in graph
    int parent[V]; // Array to store constructed MST
    int key[V]; // Key values used to pick minimum weight
                // edge in cut
    // minHeap represents set E
    struct MinHeap* minHeap = createMinHeap(V);
    // Initialize min heap with all vertices. Key value of
    // all vertices (except 0th vertex) is initially
    // infinite
    for (int v = 1; v < V; ++v) {
        parent[v] = -1;
        key[v] = INT_MAX;
        minHeap->array[v] = newMinHeapNode(v, key[v]);
        minHeap->pos[v] = v;
    }
    // Make key value of 0th vertex as 0 so that it
    // is extracted first
    key[0] = 0;
    minHeap->array[0] = newMinHeapNode(0, key[0]);
    minHeap->pos[0] = 0;
    // Initially size of min heap is equal to V
    minHeap->size = V;
    // In the following loop, min heap contains all nodes
    // not yet added to MST.
    while (!isEmpty(minHeap)) {
        // Extract the vertex with minimum key value
        struct MinHeapNode* minHeapNode
            = extractMin(minHeap);
        int u
            = minHeapNode
                  ->v; // Store the extracted vertex number
        // Traverse through all adjacent vertices of u (the
        // extracted vertex) and update their key values
        struct AdjListNode* pCrawl = graph->array[u].head;
        while (pCrawl != NULL) {
            int v = pCrawl->dest;
            // If v is not yet included in MST and weight of
            // u-v is less than key value of v, then update
            // key value and parent of v
            if (isInMinHeap(minHeap, v)
                && pCrawl->weight < key[v]) {
                key[v] = pCrawl->weight;
                parent[v] = u;
                decreaseKey(minHeap, v, key[v]);
            }
            pCrawl = pCrawl->next;
        }
    }
    // print edges of MST
    printArr(parent, V);
}
// Driver program to test above functions
int main()
{
    // Let us create the graph given in above figure
    int V = 9;
    struct Graph* graph = createGraph(V);
    addEdge(graph, 0, 1, 4);
    addEdge(graph, 0, 7, 8);
    addEdge(graph, 1, 2, 8);
    addEdge(graph, 1, 7, 11);
    addEdge(graph, 2, 3, 7);
    addEdge(graph, 2, 8, 2);
    addEdge(graph, 2, 5, 4);
    addEdge(graph, 3, 4, 9);
    addEdge(graph, 3, 5, 14);
    addEdge(graph, 4, 5, 10);
    addEdge(graph, 5, 6, 2);
    addEdge(graph, 6, 7, 1);
    addEdge(graph, 6, 8, 6);
    addEdge(graph, 7, 8, 7);
    PrimMST(graph);
    return 0;
}
````
````java
// java program for Prim's MST for adjacency list
// representation of graph
import java.util.ArrayList;
import java.util.PriorityQueue;
public class Main {
    static class Graph {
        int V;
        ArrayList<ArrayList<Node>> adj;
        // Inner class to represent an edge (destination and weight)
        static class Node {
            int dest;
            int weight;
            Node(int dest, int weight) {
                this.dest = dest;
                this.weight = weight;
            }
        }
        Graph(int V) {
            this.V = V;
            adj = new ArrayList<>(V);
            for (int i = 0; i < V; i++)
                adj.add(new ArrayList<>());
        }
        // Function to add an undirected edge between two vertices with given weight
        void addEdge(int src, int dest, int weight) {
            adj.get(src).add(new Node(dest, weight));
            adj.get(dest).add(new Node(src, weight));
        }
        // Function to find the Minimum Spanning Tree using Prim's algorithm
        void primMST() {
            int[] parent = new int[V];
            int[] key = new int[V];
            boolean[] inMST = new boolean[V];
            for (int i = 0; i < V; i++) {
                parent[i] = -1;          // Array to store the parent node of each vertex in the MST
                key[i] = Integer.MAX_VALUE;  // Array to store the minimum key value for each vertex
                inMST[i] = false;        // Array to track if the vertex is in the MST or not
            }
            PriorityQueue<Node> minHeap = new PriorityQueue<>((a, b) -> a.weight - b.weight);
            key[0] = 0;                     // Start the MST from vertex 0
            minHeap.add(new Node(0, key[0]));
            while (!minHeap.isEmpty()) {
                Node u = minHeap.poll();    // Extract the node with the minimum key value
                int uVertex = u.dest;
                inMST[uVertex] = true;
                // Traverse through all adjacent vertices of u (the extracted vertex) and update their key values
                for (Node v : adj.get(uVertex)) {
                    int vVertex = v.dest;
                    int weight = v.weight;
                    // If v is not yet included in MST and weight of u-v is less than key value of v, then update key value and parent of v
                    if (!inMST[vVertex] && weight < key[vVertex]) {
                        parent[vVertex] = uVertex;
                        key[vVertex] = weight;
                        minHeap.add(new Node(vVertex, key[vVertex]));
                    }
                }
            }
            printMST(parent);
        }
        // Function to print the edges of the Minimum Spanning Tree
        void printMST(int[] parent) {
            System.out.println("Edges of Minimum Spanning Tree:");
            for (int i = 1; i < V; i++) {
                System.out.println(parent[i] + " - " + i);
            }
        }
    }
    public static void main(String[] args) {
        int V = 9;
        Graph graph = new Graph(V);
        graph.addEdge(0, 1, 4);
        graph.addEdge(0, 7, 8);
        graph.addEdge(1, 2, 8);
        graph.addEdge(1, 7, 11);
        graph.addEdge(2, 3, 7);
        graph.addEdge(2, 8, 2);
        graph.addEdge(2, 5, 4);
        graph.addEdge(3, 4, 9);
        graph.addEdge(3, 5, 14);
        graph.addEdge(4, 5, 10);
        graph.addEdge(5, 6, 2);
        graph.addEdge(6, 7, 1);
        graph.addEdge(6, 8, 6);
        graph.addEdge(7, 8, 7);
        graph.primMST();
    }
}
````
````python3
# A Python program for Prims's MST for
# adjacency list representation of graph
from collections import defaultdict
import sys
class Heap():
    def __init__(self):
        self.array = []
        self.size = 0
        self.pos = []
    def newMinHeapNode(self, v, dist):
        minHeapNode = [v, dist]
        return minHeapNode
    # A utility function to swap two nodes of
    # min heap. Needed for min heapify
    def swapMinHeapNode(self, a, b):
        t = self.array[a]
        self.array[a] = self.array[b]
        self.array[b] = t
    # A standard function to heapify at given idx
    # This function also updates position of nodes
    # when they are swapped. Position is needed
    # for decreaseKey()
    def minHeapify(self, idx):
        smallest = idx
        left = 2 * idx + 1
        right = 2 * idx + 2
        if left < self.size and self.array[left][1] < \
                self.array[smallest][1]:
            smallest = left
        if right < self.size and self.array[right][1] < \
                self.array[smallest][1]:
            smallest = right
        # The nodes to be swapped in min heap
        # if idx is not smallest
        if smallest != idx:
            # Swap positions
            self.pos[self.array[smallest][0]] = idx
            self.pos[self.array[idx][0]] = smallest
            # Swap nodes
            self.swapMinHeapNode(smallest, idx)
            self.minHeapify(smallest)
    # Standard function to extract minimum node from heap
    def extractMin(self):
        # Return NULL wif heap is empty
        if self.isEmpty() == True:
            return
        # Store the root node
        root = self.array[0]
        # Replace root node with last node
        lastNode = self.array[self.size - 1]
        self.array[0] = lastNode
        # Update position of last node
        self.pos[lastNode[0]] = 0
        self.pos[root[0]] = self.size - 1
        # Reduce heap size and heapify root
        self.size -= 1
        self.minHeapify(0)
        return root
    def isEmpty(self):
        return True if self.size == 0 else False
    def decreaseKey(self, v, dist):
        # Get the index of v in  heap array
        i = self.pos[v]
        # Get the node and update its dist value
        self.array[i][1] = dist
        # Travel up while the complete tree is not
        # heapified. This is a O(Logn) loop
        while i > 0 and self.array[i][1] < \
                self.array[(i - 1) // 2][1]:
            # Swap this node with its parent
            self.pos[self.array[i][0]] = (i-1)/2
            self.pos[self.array[(i-1)//2][0]] = i
            self.swapMinHeapNode(i, (i - 1)//2)
            # move to parent index
            i = (i - 1) // 2
    # A utility function to check if a given vertex
    # 'v' is in min heap or not
    def isInMinHeap(self, v):
        if self.pos[v] < self.size:
            return True
        return False
def printArr(parent, n):
    for i in range(1, n):
        print("% d - % d" % (parent[i], i))
class Graph():
    def __init__(self, V):
        self.V = V
        self.graph = defaultdict(list)
    # Adds an edge to an undirected graph
    def addEdge(self, src, dest, weight):
        # Add an edge from src to dest.  A new node is
        # added to the adjacency list of src. The node
        # is added at the beginning. The first element of
        # the node has the destination and the second
        # elements has the weight
        newNode = [dest, weight]
        self.graph[src].insert(0, newNode)
        # Since graph is undirected, add an edge from
        # dest to src also
        newNode = [src, weight]
        self.graph[dest].insert(0, newNode)
    # The main function that prints the Minimum
    # Spanning Tree(MST) using the Prim's Algorithm.
    # It is a O(ELogV) function
    def PrimMST(self):
        # Get the number of vertices in graph
        V = self.V
        # key values used to pick minimum weight edge in cut
        key = []
        # List to store constructed MST
        parent = []
        # minHeap represents set E
        minHeap = Heap()
        # Initialize min heap with all vertices. Key values of all
        # vertices (except the 0th vertex) is initially infinite
        for v in range(V):
            parent.append(-1)
            key.append(1e7)
            minHeap.array.append(minHeap.newMinHeapNode(v, key[v]))
            minHeap.pos.append(v)
        # Make key value of 0th vertex as 0 so
        # that it is extracted first
        minHeap.pos[0] = 0
        key[0] = 0
        minHeap.decreaseKey(0, key[0])
        # Initially size of min heap is equal to V
        minHeap.size = V
        # In the following loop, min heap contains all nodes
        # not yet added in the MST.
        while minHeap.isEmpty() == False:
            # Extract the vertex with minimum distance value
            newHeapNode = minHeap.extractMin()
            u = newHeapNode[0]
            # Traverse through all adjacent vertices of u
            # (the extracted vertex) and update their
            # distance values
            for pCrawl in self.graph[u]:
                v = pCrawl[0]
                # If shortest distance to v is not finalized
                # yet, and distance to v through u is less than
                # its previously calculated distance
                if minHeap.isInMinHeap(v) and pCrawl[1] < key[v]:
                    key[v] = pCrawl[1]
                    parent[v] = u
                    # update distance value in min heap also
                    minHeap.decreaseKey(v, key[v])
        printArr(parent, V)
# Driver program to test the above functions
graph = Graph(9)
graph.addEdge(0, 1, 4)
graph.addEdge(0, 7, 8)
graph.addEdge(1, 2, 8)
graph.addEdge(1, 7, 11)
graph.addEdge(2, 3, 7)
graph.addEdge(2, 8, 2)
graph.addEdge(2, 5, 4)
graph.addEdge(3, 4, 9)
graph.addEdge(3, 5, 14)
graph.addEdge(4, 5, 10)
graph.addEdge(5, 6, 2)
graph.addEdge(6, 7, 1)
graph.addEdge(6, 8, 6)
graph.addEdge(7, 8, 7)
graph.PrimMST()
# This code is contributed by Divyanshu Mehta
````
````csharp
using System;
using System.Collections.Generic;
// A structure to represent a node in adjacency list
class AdjListNode
{
    public int dest;
    public int weight;
    public AdjListNode next;
}
// A structure to represent an adjacency list
class AdjList
{
    public AdjListNode head;
}
// A structure to represent a graph. A graph is an array of
// adjacency lists. Size of array will be V (number of
// vertices in graph)
class Graph
{
    public int V;
    public AdjList[] array;
}
class Program
{
    // A utility function to create a new adjacency list node
    static AdjListNode newAdjListNode(int dest, int weight)
    {
        AdjListNode newNode = new AdjListNode();
        newNode.dest = dest;
        newNode.weight = weight;
        newNode.next = null;
        return newNode;
    }
    // A utility function that creates a graph of V vertices
    static Graph createGraph(int V)
    {
        Graph graph = new Graph();
        graph.V = V;
        graph.array = new AdjList[V];
        for (int i = 0; i < V; ++i)
            graph.array[i] = new AdjList();
        return graph;
    }
    // Adds an edge to an undirected graph
    static void addEdge(Graph graph, int src, int dest, int weight)
    {
        AdjListNode newNode = newAdjListNode(dest, weight);
        newNode.next = graph.array[src].head;
        graph.array[src].head = newNode;
        newNode = newAdjListNode(src, weight);
        newNode.next = graph.array[dest].head;
        graph.array[dest].head = newNode;
    }
    // Structure to represent a min heap node
    class MinHeapNode
    {
        public int v;
        public int key;
    }
    // Structure to represent a min heap
    class MinHeap
    {
        public int size;
        public int capacity;
        public int[] pos;
        public MinHeapNode[] array;
    }
    // A utility function to create a new Min Heap Node
    static MinHeapNode newMinHeapNode(int v, int key)
    {
        MinHeapNode minHeapNode = new MinHeapNode();
        minHeapNode.v = v;
        minHeapNode.key = key;
        return minHeapNode;
    }
    // A utility function to create a Min Heap
    static MinHeap createMinHeap(int capacity)
    {
        MinHeap minHeap = new MinHeap();
        minHeap.pos = new int[capacity];
        minHeap.size = 0;
        minHeap.capacity = capacity;
        minHeap.array = new MinHeapNode[capacity];
        return minHeap;
    }
    // A utility function to swap two nodes of min heap
    static void swapMinHeapNode(ref MinHeapNode a, ref MinHeapNode b)
    {
        MinHeapNode t = a;
        a = b;
        b = t;
    }
    // A standard function to heapify at given idx
    // This function also updates position of nodes when they
    // are swapped. Position is needed for decreaseKey()
    static void minHeapify(MinHeap minHeap, int idx)
    {
        int smallest, left, right;
        smallest = idx;
        left = 2 * idx + 1;
        right = 2 * idx + 2;
        if (left < minHeap.size && minHeap.array[left].key < minHeap.array[smallest].key)
            smallest = left;
        if (right < minHeap.size && minHeap.array[right].key < minHeap.array[smallest].key)
            smallest = right;
        if (smallest != idx)
        {
            MinHeapNode smallestNode = minHeap.array[smallest];
            MinHeapNode idxNode = minHeap.array[idx];
            minHeap.pos[smallestNode.v] = idx;
            minHeap.pos[idxNode.v] = smallest;
            swapMinHeapNode(ref minHeap.array[smallest], ref minHeap.array[idx]);
            minHeapify(minHeap, smallest);
        }
    }
    // A utility function to check if the given minHeap is empty or not
    static bool isEmpty(MinHeap minHeap)
    {
        return minHeap.size == 0;
    }
    // Standard function to extract minimum node from heap
    static MinHeapNode extractMin(MinHeap minHeap)
    {
        if (isEmpty(minHeap))
            return null;
        MinHeapNode root = minHeap.array[0];
        MinHeapNode lastNode = minHeap.array[minHeap.size - 1];
        minHeap.array[0] = lastNode;
        minHeap.pos[root.v] = minHeap.size - 1;
        minHeap.pos[lastNode.v] = 0;
        --minHeap.size;
        minHeapify(minHeap, 0);
        return root;
    }
    // Function to decrease key value of a given vertex v.
    // This function uses pos[] of min heap to get the current index
    // of node in min heap
    static void decreaseKey(MinHeap minHeap, int v, int key)
    {
        int i = minHeap.pos[v];
        minHeap.array[i].key = key;
        while (i > 0 && minHeap.array[i].key < minHeap.array[(i - 1) / 2].key)
        {
            minHeap.pos[minHeap.array[i].v] = (i - 1) / 2;
            minHeap.pos[minHeap.array[(i - 1) / 2].v] = i;
            swapMinHeapNode(ref minHeap.array[i], ref minHeap.array[(i - 1) / 2]);
            i = (i - 1) / 2;
        }
    }
    // A utility function to check if a given vertex 'v' is in min heap or not
    static bool isInMinHeap(MinHeap minHeap, int v)
    {
        return minHeap.pos[v] < minHeap.size;
    }
    // A utility function used to print the constructed MST
    static void printArr(int[] arr, int n)
    {
        for (int i = 1; i < n; ++i)
            Console.WriteLine(arr[i] + " - " + i);
    }
    // The main function that constructs Minimum Spanning Tree (MST) using Prim's algorithm
    static void PrimMST(Graph graph)
    {
        int V = graph.V;
        int[] parent = new int[V];
        int[] key = new int[V];
        MinHeap minHeap = createMinHeap(V);
        for (int v = 1; v < V; ++v)
        {
            parent[v] = -1;
            key[v] = int.MaxValue;
            minHeap.array[v] = newMinHeapNode(v, key[v]);
            minHeap.pos[v] = v;
        }
        key[0] = 0;
        minHeap.array[0] = newMinHeapNode(0, key[0]);
        minHeap.pos[0] = 0;
        minHeap.size = V;
        while (!isEmpty(minHeap))
        {
            MinHeapNode minHeapNode = extractMin(minHeap);
            int u = minHeapNode.v;
            AdjListNode pCrawl = graph.array[u].head;
            while (pCrawl != null)
            {
                int v = pCrawl.dest;
                if (isInMinHeap(minHeap, v) && pCrawl.weight < key[v])
                {
                    key[v] = pCrawl.weight;
                    parent[v] = u;
                    decreaseKey(minHeap, v, key[v]);
                }
                pCrawl = pCrawl.next;
            }
        }
        printArr(parent, V);
    }
    static void Main(string[] args)
    {
        int V = 9;
        Graph graph = createGraph(V);
        addEdge(graph, 0, 1, 4);
        addEdge(graph, 0, 7, 8);
        addEdge(graph, 1, 2, 8);
        addEdge(graph, 1, 7, 11);
        addEdge(graph, 2, 3, 7);
        addEdge(graph, 2, 8, 2);
        addEdge(graph, 2, 5, 4);
        addEdge(graph, 3, 4, 9);
        addEdge(graph, 3, 5, 14);
        addEdge(graph, 4, 5, 10);
        addEdge(graph, 5, 6, 2);
        addEdge(graph, 6, 7, 1);
        addEdge(graph, 6, 8, 6);
        addEdge(graph, 7, 8, 7);
        PrimMST(graph);
    }
}
````
````javascript
<script>
// Javascript program for Prim's MST for
// adjacency list representation of graph
class node1
{
    constructor(a,b)
    {
        this.dest = a;
        this.weight = b;
    }
}
class Graph
{
    constructor(e)
    {
        this.V=e;
        this.adj = new Array(V);
        for (let o = 0; o < V; o++)
            this.adj[o] = [];
    }
}
// class to represent a node in PriorityQueue
    // Stores a vertex and its corresponding
    // key value
class node
{
    constructor()
    {
        this.vertex=0;
        this.key=0;
    }
}
// method to add an edge
    // between two vertices
function addEdge(graph,src,dest,weight)
{
    let node0 = new node1(dest, weight);
        let node = new node1(src, weight);
        graph.adj[src].push(node0);
        graph.adj[dest].push(node);
}
// method used to find the mst
function prims_mst(graph)
{
    // Whether a vertex is in PriorityQueue or not
        let mstset = new Array(graph.V);
        let e = new Array(graph.V);
        // Stores the parents of a vertex
        let parent = new Array(graph.V);
        for (let o = 0; o < graph.V; o++)
        {
            e[o] = new node();
          }
        for (let o = 0; o < graph.V; o++) {
            // Initialize to false
            mstset[o] = false;
            // Initialize key values to infinity
            e[o].key = Number.MAX_VALUE;
            e[o].vertex = o;
            parent[o] = -1;
        }
        // Include the source vertex in mstset
        mstset[0] = true;
        // Set key value to 0
        // so that it is extracted first
        // out of PriorityQueue
        e[0].key = 0;
        // Use TreeSet instead of PriorityQueue as the remove function of the PQ is O(n) in java.
        let queue = [];
        for (let o = 0; o < graph.V; o++)
            queue.push(e[o]);
        queue.sort(function(a,b){return a.key-b.key;});
        // Loops until the queue is not empty
        while (queue.length!=0) {
            // Extracts a node with min key value
            let node0 = queue.shift();
            // Include that node into mstset
            mstset[node0.vertex] = true;
            // For all adjacent vertex of the extracted vertex V
            for (let iterator of graph.adj[node0.vertex].values()) {
                // If V is in queue
                if (mstset[iterator.dest] == false) {
                    // If the key value of the adjacent vertex is
                    // more than the extracted key
                    // update the key value of adjacent vertex
                    // to update first remove and add the updated vertex
                    if (e[iterator.dest].key > iterator.weight) {
                        queue.splice(queue.indexOf(e[iterator.dest]),1);
                        e[iterator.dest].key = iterator.weight;
                        queue.push(e[iterator.dest]);
                        queue.sort(function(a,b){return a.key-b.key;});
                        parent[iterator.dest] = node0.vertex;
                    }
                }
            }
        }
        // Prints the vertex pair of mst
        for (let o = 1; o < graph.V; o++)
            document.write(parent[o] + " "
                               + "-"
                               + " " + o+"<br>");
}
let V = 9;
let graph = new Graph(V);
addEdge(graph, 0, 1, 4);
addEdge(graph, 0, 7, 8);
addEdge(graph, 1, 2, 8);
addEdge(graph, 1, 7, 11);
addEdge(graph, 2, 3, 7);
addEdge(graph, 2, 8, 2);
addEdge(graph, 2, 5, 4);
addEdge(graph, 3, 4, 9);
addEdge(graph, 3, 5, 14);
addEdge(graph, 4, 5, 10);
addEdge(graph, 5, 6, 2);
addEdge(graph, 6, 7, 1);
addEdge(graph, 6, 8, 6);
addEdge(graph, 7, 8, 7);
// Method invoked
prims_mst(graph);
// This code is contributed by avanitrachhadiya2155
</script>
````
**Output**
```
0 - 1
5 - 2
2 - 3
3 - 4
6 - 5
7 - 6
0 - 7
2 - 8
```
**Time Complexity:**
The time complexity of the above code/algorithm looks O(V^2) as there are two nested while loops. If we take a closer look, we can observe that the statements in inner loop are executed O(V+E) times (similar to BFS). The inner loop has decreaseKey() operation which takes O(LogV) time. So overall time complexity is O(E+V)\*O(LogV) which is O((E+V)\*LogV) = O(ELogV) (For a connected graph, V = O(E))
**Space Complexity:**
The space complexity of the above code/algorithm is O(V + E) because we need to store the adjacency list representation of the graph, the heap data structure, and the MST.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dsa/prims-mst-for-adjacency-list-representation-greedy-algo-6/)

## GATE CS

- Subject: Algorithms
- Topic: Greedy Techniques

> [!note] Related notes
>
> - [[Dijkstra’s Algorithm for Adjacency List Representation]]
> - [[Efficient Huffman Coding for Sorted Input]]
> - [[Fractional Knapsack Problem]]
> - [[Introduction to Greedy Algorithms]]
> - [[Optimal File Merge Patterns]]
> - [[Prim’s Minimum Spanning Tree]]
> - [[Applications of Depth First Search]]
> - [[Asymptotic Notations]]
> - [[Binary Search]]
> - [[Breadth First Traversal or BFS for a Graph]]

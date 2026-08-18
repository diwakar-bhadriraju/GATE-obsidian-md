---
title: "Dijkstra’s Algorithm for Adjacency List Representation | Greedy Algo-8"
subject: "Algorithms"
topic: "Greedy Techniques"
source: "https://www.geeksforgeeks.org/dsa/dijkstras-algorithm-for-adjacency-list-representation-greedy-algo-8/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Algorithms/Greedy Techniques"
tags:
  - gate/cs
  - subject/algorithms
  - topic/greedy-techniques
---


> [!abstract] Dijkstra’s Algorithm for Adjacency List Representation | Greedy Algo-8
> 
> **Subject:** `Algorithms` &nbsp;|&nbsp; **Topic:** `Greedy Techniques`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dsa/dijkstras-algorithm-for-adjacency-list-representation-greedy-algo-8/)

---

# Dijkstra’s Algorithm for Adjacency List Representation | Greedy Algo-8

The Dijkstra's Algorithm, we can either use the matrix representation or the adjacency list representation to represent the graph, while the time complexity of Dijkstra's Algorithm using matrix representation is O(V^2). The time complexity of Dijkstra's Algorithm using adjacency list representation is O(ELogV). The adjacency list representation not only reduces the space used by this algorithm but also optimizes its time complexity.
**Examples:**
> **Input:**  src = 0, the graph is shown below.
>
> ![1-(2)](assets/Working-of-Dijkstras-Algorithm-768-458e72f6a1.jpg)
>
> **Output:**  0 4 12 19 21 11 9 8 14
> **Explanation:**  Shortest Paths:
> 0 to 1 = 4.
> 0 to 2 = 12. 0->1->2
> 0 to 3 = 19. 0->1->2->3
> 0 to 4 = 21. 0->7->6->5->4
> 0 to 5 = 11. 0->7->6->5
> 0 to 6 = 9. 0->7->6
> 0 to 7 = 8. 0->7
> 0 to 8 = 14. 0->1->2->8
In Dijkstra's algorithm, two sets are maintained where one set contains a list of vertices already included in SPT (Shortest Path Tree), and another set contains vertices not yet included. With adjacency list representation, all vertices of a graph can be traversed in O(V+E) time using [BFS](https://www.geeksforgeeks.org/dsa/breadth-first-search-or-bfs-for-a-graph/).
The idea is to traverse all vertices of the graph using [BFS](https://www.geeksforgeeks.org/dsa/breadth-first-search-or-bfs-for-a-graph/)and use a Min Heap to store the vertices not yet included in SPT (or the vertices for which the shortest distance is not finalized yet).  Min Heap is used as a priority queue to get the minimum distance vertex from a set of not-yet-included vertices.
### **Dijkstra’s Algorithm for Adjacency List Representation using Min heap**
1. Create a Min Heap of size V where V is the number of vertices in the graph. Every node of the min-heap contains the vertex number and distance value of the vertex.
2. Initialize Min Heap with source vertex as root (the distance value assigned to source vertex is 0). The distance value assigned to all other vertices is INF (infinite).
3. While Min Heap is not empty, do the following :
   1. Extract the vertex with minimum distance value node from Min Heap. Let the extracted vertex be u.
   2. For every adjacent vertex v of u, check if v is in the Min Heap. If v is in the Min Heap and the distance value is more than the weight of u-v plus the distance value of u, then update the distance value of v.
Let us understand with the following example. Let the given source vertex be 0 
- Initially, the distance value of the source vertex is 0, and INF (infinite) for all other vertices. So source vertex is extracted from Min Heap and distance values of vertices adjacent to 0 (1 and 7) are updated.
- The vertices in the sptset are the vertices for which minimum distances are finalized and are not in Min Heap.
- Since the distance value of vertex 1 is minimum among all nodes in Min Heap, it is extracted from Min Heap, and distance values of vertices adjacent to 1 are updated (distance is updated if the vertex is in Min Heap and distance through 1 is shorter than the previous distance).
- Pick the vertex with a minimum distance value from the min-heap. Vertex 7 is picked. So min-heap now contains all vertices except 0, 1, and 7. Update the distance values of adjacent vertices of 7. The distance value of vertex 6 and 8 becomes finite (15 and 9 respectively).
- Pick the vertex with a minimum distance from the min-heap. Vertex 6 is picked, and the distance values of adjacent vertices of 6 are updated. The distance values of vertex 5 and 8 are updated.
- The above steps are repeated till the min-heap doesn't become empty. Finally, we get the following shortest path tree.
````cpp
// C / C++ program for Dijkstra's
// shortest path algorithm for adjacency
// list representation of graph
#include <stdio.h>
#include <stdlib.h>
#include <limits.h>
// A structure to represent a
// node in adjacency list
struct AdjListNode
{
    int dest;
    int weight;
    struct AdjListNode* next;
};
// A structure to represent
// an adjacency list
struct AdjList
{
   // Pointer to head node of list
   struct AdjListNode *head;
};
// A structure to represent a graph.
// A graph is an array of adjacency lists.
// Size of array will be V (number of
// vertices in graph)
struct Graph
{
    int V;
    struct AdjList* array;
};
// A utility function to create
// a new adjacency list node
struct AdjListNode* newAdjListNode(
                   int dest, int weight)
{
    struct AdjListNode* newNode =
            (struct AdjListNode*)
      malloc(sizeof(struct AdjListNode));
    newNode->dest = dest;
    newNode->weight = weight;
    newNode->next = NULL;
    return newNode;
}
// A utility function that creates
// a graph of V vertices
struct Graph* createGraph(int V)
{
    struct Graph* graph = (struct Graph*)
            malloc(sizeof(struct Graph));
    graph->V = V;
    // Create an array of adjacency lists.
    // Size of array will be V
    graph->array = (struct AdjList*)
       malloc(V * sizeof(struct AdjList));
    // Initialize each adjacency list
    // as empty by making head as NULL
    for (int i = 0; i < V; ++i)
        graph->array[i].head = NULL;
    return graph;
}
// Adds an edge to an undirected graph
void addEdge(struct Graph* graph, int src,
                   int dest, int weight)
{
    // Add an edge from src to dest.
    // A new node is added to the adjacency
    // list of src.  The node is
    // added at the beginning
    struct AdjListNode* newNode =
            newAdjListNode(dest, weight);
    newNode->next = graph->array[src].head;
    graph->array[src].head = newNode;
    // Since graph is undirected,
    // add an edge from dest to src also
    newNode = newAdjListNode(src, weight);
    newNode->next = graph->array[dest].head;
    graph->array[dest].head = newNode;
}
// Structure to represent a min heap node
struct MinHeapNode
{
    int  v;
    int dist;
};
// Structure to represent a min heap
struct MinHeap
{
    // Number of heap nodes present currently
    int size;
    // Capacity of min heap
    int capacity;
    // This is needed for decreaseKey()
    int *pos;
    struct MinHeapNode **array;
};
// A utility function to create a
// new Min Heap Node
struct MinHeapNode* newMinHeapNode(int v,
                                 int dist)
{
    struct MinHeapNode* minHeapNode =
           (struct MinHeapNode*)
      malloc(sizeof(struct MinHeapNode));
    minHeapNode->v = v;
    minHeapNode->dist = dist;
    return minHeapNode;
}
// A utility function to create a Min Heap
struct MinHeap* createMinHeap(int capacity)
{
    struct MinHeap* minHeap =
         (struct MinHeap*)
      malloc(sizeof(struct MinHeap));
    minHeap->pos = (int *)malloc(
            capacity * sizeof(int));
    minHeap->size = 0;
    minHeap->capacity = capacity;
    minHeap->array =
         (struct MinHeapNode**)
                 malloc(capacity *
       sizeof(struct MinHeapNode*));
    return minHeap;
}
// A utility function to swap two
// nodes of min heap.
// Needed for min heapify
void swapMinHeapNode(struct MinHeapNode** a,
                     struct MinHeapNode** b)
{
    struct MinHeapNode* t = *a;
    *a = *b;
    *b = t;
}
// A standard function to
// heapify at given idx
// This function also updates
// position of nodes when they are swapped.
// Position is needed for decreaseKey()
void minHeapify(struct MinHeap* minHeap,
                                  int idx)
{
    int smallest, left, right;
    smallest = idx;
    left = 2 * idx + 1;
    right = 2 * idx + 2;
    if (left < minHeap->size &&
        minHeap->array[left]->dist <
         minHeap->array[smallest]->dist )
      smallest = left;
    if (right < minHeap->size &&
        minHeap->array[right]->dist <
         minHeap->array[smallest]->dist )
      smallest = right;
    if (smallest != idx)
    {
        // The nodes to be swapped in min heap
        MinHeapNode *smallestNode =
             minHeap->array[smallest];
        MinHeapNode *idxNode =
                 minHeap->array[idx];
        // Swap positions
        minHeap->pos[smallestNode->v] = idx;
        minHeap->pos[idxNode->v] = smallest;
        // Swap nodes
        swapMinHeapNode(&minHeap->array[smallest],
                         &minHeap->array[idx]);
        minHeapify(minHeap, smallest);
    }
}
// A utility function to check if
// the given minHeap is empty or not
int isEmpty(struct MinHeap* minHeap)
{
    return minHeap->size == 0;
}
// Standard function to extract
// minimum node from heap
struct MinHeapNode* extractMin(struct MinHeap*
                                   minHeap)
{
    if (isEmpty(minHeap))
        return NULL;
    // Store the root node
    struct MinHeapNode* root =
                   minHeap->array[0];
    // Replace root node with last node
    struct MinHeapNode* lastNode =
         minHeap->array[minHeap->size - 1];
    minHeap->array[0] = lastNode;
    // Update position of last node
    minHeap->pos[root->v] = minHeap->size-1;
    minHeap->pos[lastNode->v] = 0;
    // Reduce heap size and heapify root
    --minHeap->size;
    minHeapify(minHeap, 0);
    return root;
}
// Function to decreasekey dist value
// of a given vertex v. This function
// uses pos[] of min heap to get the
// current index of node in min heap
void decreaseKey(struct MinHeap* minHeap,
                         int v, int dist)
{
    // Get the index of v in  heap array
    int i = minHeap->pos[v];
    // Get the node and update its dist value
    minHeap->array[i]->dist = dist;
    // Travel up while the complete
    // tree is not heapified.
    // This is a O(Logn) loop
    while (i && minHeap->array[i]->dist <
           minHeap->array[(i - 1) / 2]->dist)
    {
        // Swap this node with its parent
        minHeap->pos[minHeap->array[i]->v] =
                                      (i-1)/2;
        minHeap->pos[minHeap->array[
                             (i-1)/2]->v] = i;
        swapMinHeapNode(&minHeap->array[i],
                 &minHeap->array[(i - 1) / 2]);
        // move to parent index
        i = (i - 1) / 2;
    }
}
// A utility function to check if a given vertex
// 'v' is in min heap or not
bool isInMinHeap(struct MinHeap *minHeap, int v)
{
   if (minHeap->pos[v] < minHeap->size)
     return true;
   return false;
}
// A utility function used to print the solution
void printArr(int dist[], int n)
{
    printf("Vertex   Distance from Source\n");
    for (int i = 0; i < n; ++i)
        printf("%d \t\t %d\n", i, dist[i]);
}
// The main function that calculates
// distances of shortest paths from src to all
// vertices. It is a O(ELogV) function
void dijkstra(struct Graph* graph, int src)
{
    // Get the number of vertices in graph
    int V = graph->V;
    // dist values used to pick
    // minimum weight edge in cut
    int dist[V];
    // minHeap represents set E
    struct MinHeap* minHeap = createMinHeap(V);
    // Initialize min heap with all
    // vertices. dist value of all vertices
    for (int v = 0; v < V; ++v)
    {
        dist[v] = INT_MAX;
        minHeap->array[v] = newMinHeapNode(v,
                                      dist[v]);
        minHeap->pos[v] = v;
    }
    // Make dist value of src vertex
    // as 0 so that it is extracted first
    minHeap->array[src] =
          newMinHeapNode(src, dist[src]);
    minHeap->pos[src]   = src;
    dist[src] = 0;
    decreaseKey(minHeap, src, dist[src]);
    // Initially size of min heap is equal to V
    minHeap->size = V;
    // In the following loop,
    // min heap contains all nodes
    // whose shortest distance
    // is not yet finalized.
    while (!isEmpty(minHeap))
    {
        // Extract the vertex with
        // minimum distance value
        struct MinHeapNode* minHeapNode =
                     extractMin(minHeap);
        // Store the extracted vertex number
        int u = minHeapNode->v;
        // Traverse through all adjacent
        // vertices of u (the extracted
        // vertex) and update
        // their distance values
        struct AdjListNode* pCrawl =
                     graph->array[u].head;
        while (pCrawl != NULL)
        {
            int v = pCrawl->dest;
            // If shortest distance to v is
            // not finalized yet, and distance to v
            // through u is less than its
            // previously calculated distance
            if (isInMinHeap(minHeap, v) &&
                      dist[u] != INT_MAX &&
              pCrawl->weight + dist[u] < dist[v])
            {
                dist[v] = dist[u] + pCrawl->weight;
                // update distance
                // value in min heap also
                decreaseKey(minHeap, v, dist[v]);
            }
            pCrawl = pCrawl->next;
        }
    }
    // print the calculated shortest distances
    printArr(dist, V);
}
int main()
{
    // create the graph given in above figure
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
    dijkstra(graph, 0);
    return 0;
}
````
````java
import java.io.*;
import java.util.*;
class GFG {
    static class AdjListNode {
        int vertex, weight;
        AdjListNode(int v, int w)
        {
            vertex = v;
            weight = w;
        }
        int getVertex() { return vertex; }
        int getWeight() { return weight; }
    }
    // Function to find the shortest distance of all the
    // vertices from the source vertex S.
    public static int[] dijkstra(
        int V, ArrayList<ArrayList<AdjListNode> > graph,
        int src)
    {
        int[] distance = new int[V];
        for (int i = 0; i < V; i++)
            distance[i] = Integer.MAX_VALUE;
        distance[src] = 0;
        PriorityQueue<AdjListNode> pq = new PriorityQueue<>(
            (v1, v2) -> v1.getWeight() - v2.getWeight());
        pq.add(new AdjListNode(src, 0));
        while (pq.size() > 0) {
            AdjListNode current = pq.poll();
            for (AdjListNode n :
                 graph.get(current.getVertex())) {
                if (distance[current.getVertex()]
                        + n.getWeight()
                    < distance[n.getVertex()]) {
                    distance[n.getVertex()]
                        = n.getWeight()
                          + distance[current.getVertex()];
                    pq.add(new AdjListNode(
                        n.getVertex(),
                        distance[n.getVertex()]));
                }
            }
        }
        // If you want to calculate distance from source to
        // a particular target, you can return
        // distance[target]
        return distance;
    }
    public static void main(String[] args)
    {
        int V = 9;
        ArrayList<ArrayList<AdjListNode> > graph
            = new ArrayList<>();
        for (int i = 0; i < V; i++) {
            graph.add(new ArrayList<>());
        }
        int source = 0;
        graph.get(0).add(new AdjListNode(1, 4));
        graph.get(0).add(new AdjListNode(7, 8));
        graph.get(1).add(new AdjListNode(2, 8));
        graph.get(1).add(new AdjListNode(7, 11));
        graph.get(1).add(new AdjListNode(0, 7));
        graph.get(2).add(new AdjListNode(1, 8));
        graph.get(2).add(new AdjListNode(3, 7));
        graph.get(2).add(new AdjListNode(8, 2));
        graph.get(2).add(new AdjListNode(5, 4));
        graph.get(3).add(new AdjListNode(2, 7));
        graph.get(3).add(new AdjListNode(4, 9));
        graph.get(3).add(new AdjListNode(5, 14));
        graph.get(4).add(new AdjListNode(3, 9));
        graph.get(4).add(new AdjListNode(5, 10));
        graph.get(5).add(new AdjListNode(4, 10));
        graph.get(5).add(new AdjListNode(6, 2));
        graph.get(6).add(new AdjListNode(5, 2));
        graph.get(6).add(new AdjListNode(7, 1));
        graph.get(6).add(new AdjListNode(8, 6));
        graph.get(7).add(new AdjListNode(0, 8));
        graph.get(7).add(new AdjListNode(1, 11));
        graph.get(7).add(new AdjListNode(6, 1));
        graph.get(7).add(new AdjListNode(8, 7));
        graph.get(8).add(new AdjListNode(2, 2));
        graph.get(8).add(new AdjListNode(6, 6));
        graph.get(8).add(new AdjListNode(7, 1));
        int[] distance = dijkstra(V, graph, source);
        // Printing the Output
        System.out.println("Vertex  "
                           + "  Distance from Source");
        for (int i = 0; i < V; i++) {
            System.out.println(i + "             "
                               + distance[i]);
        }
    }
}
````
````python3
# A Python program for Dijkstra's shortest
# path algorithm for adjacency
# list representation of graph
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
    # A utility function to swap two nodes
    # of min heap. Needed for min heapify
    def swapMinHeapNode(self, a, b):
        t = self.array[a]
        self.array[a] = self.array[b]
        self.array[b] = t
    # A standard function to heapify at given idx
    # This function also updates position of nodes
    # when they are swapped.Position is needed
    # for decreaseKey()
    def minHeapify(self, idx):
        smallest = idx
        left = 2*idx + 1
        right = 2*idx + 2
        if (left < self.size and
           self.array[left][1]
            < self.array[smallest][1]):
            smallest = left
        if (right < self.size and
           self.array[right][1]
            < self.array[smallest][1]):
            smallest = right
        # The nodes to be swapped in min
        # heap if idx is not smallest
        if smallest != idx:
            # Swap positions
            self.pos[self.array[smallest][0]] = idx
            self.pos[self.array[idx][0]] = smallest
            # Swap nodes
            self.swapMinHeapNode(smallest, idx)
            self.minHeapify(smallest)
    # Standard function to extract minimum
    # node from heap
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
        # Travel up while the complete tree is
        # not heapified. This is a O(Logn) loop
        while (i > 0 and self.array[i][1] <
                  self.array[(i - 1) // 2][1]):
            # Swap this node with its parent
            self.pos[ self.array[i][0] ] = (i-1)//2
            self.pos[ self.array[(i-1)//2][0] ] = i
            self.swapMinHeapNode(i, (i - 1)//2 )
            # move to parent index
            i = (i - 1) // 2;
    # A utility function to check if a given
    # vertex 'v' is in min heap or not
    def isInMinHeap(self, v):
        if self.pos[v] < self.size:
            return True
        return False
def printArr(dist, n):
    print ("Vertex\tDistance from source")
    for i in range(n):
        print ("%d\t\t%d" % (i,dist[i]))
class Graph():
    def __init__(self, V):
        self.V = V
        self.graph = defaultdict(list)
    # Adds an edge to an undirected graph
    def addEdge(self, src, dest, weight):
        # Add an edge from src to dest.  A new node
        # is added to the adjacency list of src. The
        # node is added at the beginning. The first
        # element of the node has the destination
        # and the second elements has the weight
        newNode = [dest, weight]
        self.graph[src].insert(0, newNode)
        # Since graph is undirected, add an edge
        # from dest to src also
        newNode = [src, weight]
        self.graph[dest].insert(0, newNode)
    # The main function that calculates distances
    # of shortest paths from src to all vertices.
    # It is a O(ELogV) function
    def dijkstra(self, src):
        V = self.V  # Get the number of vertices in graph
        dist = []   # dist values used to pick minimum
                    # weight edge in cut
        # minHeap represents set E
        minHeap = Heap()
        #  Initialize min heap with all vertices.
        # dist value of all vertices
        for v in range(V):
            dist.append(1e7)
            minHeap.array.append( minHeap.
                                newMinHeapNode(v, dist[v]))
            minHeap.pos.append(v)
        # Make dist value of src vertex as 0 so
        # that it is extracted first
        minHeap.pos[src] = src
        dist[src] = 0
        minHeap.decreaseKey(src, dist[src])
        # Initially size of min heap is equal to V
        minHeap.size = V;
        # In the following loop,
        # min heap contains all nodes
        # whose shortest distance is not yet finalized.
        while minHeap.isEmpty() == False:
            # Extract the vertex
            # with minimum distance value
            newHeapNode = minHeap.extractMin()
            u = newHeapNode[0]
            # Traverse through all adjacent vertices of
            # u (the extracted vertex) and update their
            # distance values
            for pCrawl in self.graph[u]:
                v = pCrawl[0]
                # If shortest distance to v is not finalized
                # yet, and distance to v through u is less
                # than its previously calculated distance
                if (minHeap.isInMinHeap(v) and
                     dist[u] != 1e7 and \
                   pCrawl[1] + dist[u] < dist[v]):
                        dist[v] = pCrawl[1] + dist[u]
                        # update distance value
                        # in min heap also
                        minHeap.decreaseKey(v, dist[v])
        printArr(dist,V)
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
graph.dijkstra(0)
# This code is contributed by Divyanshu Mehta
````
````csharp
// C# program for Dijkstra's
// shortest path algorithm for adjacency
// list representation of graph
using System;
using System.Collections.Generic;
using System.Linq;
public class AdjListNode : IComparable<AdjListNode> {
  private int vertex, weight;
  public AdjListNode(int v, int w)
  {
    vertex = v;
    weight = w;
  }
  public int getVertex() { return vertex; }
  public int getWeight() { return weight; }
  public int CompareTo(AdjListNode other)
  {
    return weight - other.weight;
  }
}
class GFG {
  // Function to find the shortest distance of all the
  // vertices from the source vertex S.
  public static int[] dijkstra(
    int V, List<List<AdjListNode> > graph, int src)
  {
    int[] distance = new int[V];
    for (int i = 0; i < V; i++)
      distance[i] = Int32.MaxValue;
    distance[src] = 0;
    SortedSet<AdjListNode> pq
      = new SortedSet<AdjListNode>();
    pq.Add(new AdjListNode(src, 0));
    while (pq.Count > 0) {
      AdjListNode current = pq.First();
      pq.Remove(current);
      foreach(
        AdjListNode n in graph[current.getVertex()])
      {
        if (distance[current.getVertex()]
            + n.getWeight()
            < distance[n.getVertex()]) {
          distance[n.getVertex()]
            = n.getWeight()
            + distance[current.getVertex()];
          pq.Add(new AdjListNode(
            n.getVertex(),
            distance[n.getVertex()]));
        }
      }
    }
    // If you want to calculate distance from source to
    // a particular target, you can return
    // distance[target]
    return distance;
  }
  static void Main(string[] args)
  {
    int V = 9;
    List<List<AdjListNode> > graph
      = new List<List<AdjListNode> >();
    for (int i = 0; i < V; i++) {
      graph.Add(new List<AdjListNode>());
    }
    int source = 0;
    graph[0].Add(new AdjListNode(1, 4));
    graph[0].Add(new AdjListNode(7, 8));
    graph[1].Add(new AdjListNode(2, 8));
    graph[1].Add(new AdjListNode(7, 11));
    graph[1].Add(new AdjListNode(0, 7));
    graph[2].Add(new AdjListNode(1, 8));
    graph[2].Add(new AdjListNode(3, 7));
    graph[2].Add(new AdjListNode(8, 2));
    graph[2].Add(new AdjListNode(5, 4));
    graph[3].Add(new AdjListNode(2, 7));
    graph[3].Add(new AdjListNode(4, 9));
    graph[3].Add(new AdjListNode(5, 14));
    graph[4].Add(new AdjListNode(3, 9));
    graph[4].Add(new AdjListNode(5, 10));
    graph[5].Add(new AdjListNode(4, 10));
    graph[5].Add(new AdjListNode(6, 2));
    graph[6].Add(new AdjListNode(5, 2));
    graph[6].Add(new AdjListNode(7, 1));
    graph[6].Add(new AdjListNode(8, 6));
    graph[7].Add(new AdjListNode(0, 8));
    graph[7].Add(new AdjListNode(1, 11));
    graph[7].Add(new AdjListNode(6, 1));
    graph[7].Add(new AdjListNode(8, 7));
    graph[8].Add(new AdjListNode(2, 2));
    graph[8].Add(new AdjListNode(6, 6));
    graph[8].Add(new AdjListNode(7, 1));
    int[] distance = dijkstra(V, graph, source);
    // Printing the Output
    Console.WriteLine("Vertex "
                      + " Distance from Source");
    for (int i = 0; i < V; i++) {
      Console.WriteLine(
        "{0}             {1}", i,
        distance[i]);
    }
  }
}
// This code is contributed by cavi4762.
````
````javascript
// javascript program for Dijkstra's
// shortest path algorithm for adjacency
// list representation of graph
// A structure to represent a
// node in adjacency list
class AdjListNode {
  constructor(dest, weight) {
    this.dest = dest;
    this.weight = weight;
  }
}
// Function to find the shortest distance of all the
// vertices from the source vertex S.
function dijkstra(V, graph, source) {
  let distance = [];
  let visited = [];
  for (let i = 0; i < V; i++) {
    distance.push(Infinity);
    visited.push(false);
  }
  distance[source] = 0;
  for (let i = 0; i < V - 1; i++) {
    let u = getMinDistanceVertex(distance, visited);
    visited[u] = true;
    for (let j = 0; j < graph[u].length; j++) {
      let v = graph[u][j].dest;
      let weight = graph[u][j].weight;
      if (!visited[v] && distance[u] !== Infinity && distance[u] + weight < distance[v]) {
        distance[v] = distance[u] + weight;
      }
    }
  }
  // If you want to calculate distance from source to
  // a particular target, you can return
  // distance[target]
  return distance;
}
function getMinDistanceVertex(distance, visited) {
  let minDistance = Infinity;
  let minIndex = -1;
  for (let i = 0; i < distance.length; i++) {
    if (!visited[i] && distance[i] <= minDistance) {
      minDistance = distance[i];
      minIndex = i;
    }
  }
  return minIndex;
}
// create the graph given in above figure
const V = 9;
let graph = [];
for (let i = 0; i < V; i++) {
  graph.push([]);
}
let source = 0;
graph[0].push(new AdjListNode(1, 4));
graph[0].push(new AdjListNode(7, 8));
graph[1].push(new AdjListNode(2, 8));
graph[1].push(new AdjListNode(7, 11));
graph[1].push(new AdjListNode(0, 7));
graph[2].push(new AdjListNode(1, 8));
graph[2].push(new AdjListNode(3, 7));
graph[2].push(new AdjListNode(8, 2));
graph[2].push(new AdjListNode(5, 4));
graph[3].push(new AdjListNode(2, 7));
graph[3].push(new AdjListNode(4, 9));
graph[3].push(new AdjListNode(5, 14));
graph[4].push(new AdjListNode(3, 9));
graph[4].push(new AdjListNode(5, 10));
graph[5].push(new AdjListNode(4, 10));
graph[5].push(new AdjListNode(6, 2));
graph[6].push(new AdjListNode(5, 2));
graph[6].push(new AdjListNode(7, 1));
graph[6].push(new AdjListNode(8, 6));
graph[7].push(new AdjListNode(0, 8));
graph[7].push(new AdjListNode(1, 11));
graph[7].push(new AdjListNode(6, 1));
graph[7].push(new AdjListNode(8, 7));
graph[8].push(new AdjListNode(2, 2));
graph[8].push(new AdjListNode(6, 6));
graph[8].push(new AdjListNode(7, 1));
let distance = dijkstra(V, graph, source);
// Printing the Output
console.log("Vertex Distance from Source");
for (let i = 0; i < V; i++) {
    console.log(i + " \t\t " + distance[i]);
}
// This code is contributed by shivhack999
````
**Output**
```
Vertex   Distance from Source
0          0
1          4
2          12
3          19
4          21
5          11
6          9
7          8
8          14
```
**Time Complexity:** The time complexity of the above code/algorithm looks O(V^2) as there are two nested while loops. If we take a closer look, we can observe that the statements in the inner loop are executed O(V+E) times (similar to BFS). The inner loop has a decreaseKey() operation which takes O(log V) time. So overall time complexity is O(E+V)\*O(log V) which is O((E+V)\*logV) = O(E log V) 
Note that the above code uses Binary Heap for Priority Queue implementation. Time complexity can be reduced to O(E + V logV) using the Fibonacci Heap. The reason is, that Fibonacci Heap takes O(1) time for decrease-key operation while Binary Heap takes O(logn) time.
**Space Complexity: O(V)**
The space complexity of Dijkstra’s algorithm is O(V) as we maintain two priority queues or heaps (in the case of binary heap). The heap stores the nodes that are not yet included in SPT (shortest path tree). We also maintain an array to store the distance values of each node.
### **Dijkstra’s Algorithm for Adjacency List Representation using Built-in Priority Queue (or Heap)**
> This approach shows the implementation of Dijkstra's Algorithm with a **priority queue** to extract minimum and decrease key. However, the problem is, that priority\_queue doesn’t support the decrease key. To resolve this problem, do not update a key, but insert one more copy of it. So we allow multiple instances of the same vertex in the priority queue. This approach doesn’t require decreasing key operations and has below important properties.
>
> - Whenever the distance of a vertex is reduced, we add one more instance of a vertex in priority\_queue. Even if there are multiple instances, we only consider the instance with minimum distance and ignore other instances.
> - The time complexity remains  **O(E \* LogV)**  as there will be at most O(E) vertices in the priority queue and O(logE) is the same as O(logV)
````cpp
// Program to find Dijkstra's shortest path using
// priority_queue
#include <bits/stdc++.h>
using namespace std;
// To add an edge
void addEdge(vector<pair<int, int> > adj[], int u, int v,
             int wt)
{
    adj[u].push_back(make_pair(v, wt));
    adj[v].push_back(make_pair(u, wt));
}
// Prints shortest paths from src to all other vertices
void shortestPath(vector<pair<int, int> > adj[], int V,
                  int src)
{
    // Create a priority queue to store vertices that
    // are being preprocessed.
    priority_queue<pair<int,int>, vector<pair<int,int>>, greater<pair<int,int>> >
        pq;
    // Create a vector for distances and initialize all
    // distances as infinite
    vector<int> dist(V, INT_MAX);
    // Insert source itself in priority queue and initialize
    // its distance as 0.
    pq.push(make_pair(0, src));
    dist[src] = 0;
    /* Looping till priority queue becomes empty (or all
    distances are not finalized) */
    while (!pq.empty()) {
        // The first vertex in pair is the minimum distance
        // vertex, extract it from priority queue.
        int u = pq.top().second;
        pq.pop();
        // Get all adjacent of u.
        for (auto x : adj[u]) {
            // Get vertex label and weight of current
            // adjacent of u.
            int v = x.first;
            int weight = x.second;
            // If there is shorted path to v through u.
            if (dist[v] > dist[u] + weight) {
                // Updating distance of v
                dist[v] = dist[u] + weight;
                pq.push(make_pair(dist[v], v));
            }
        }
    }
    // Print shortest distances stored in dist[]
    printf("Vertex \tDistance from Source\n");
    for (int i = 0; i < V; ++i)
        printf("%d \t\t %d\n", i, dist[i]);
}
// Driver program to test methods of graph class
int main()
{
    int V = 9;
    vector<pair<int,int>> adj[V];
    // making above shown graph
    addEdge(adj, 0, 1, 4);
    addEdge(adj, 0, 7, 8);
    addEdge(adj, 1, 2, 8);
    addEdge(adj, 1, 7, 11);
    addEdge(adj, 2, 3, 7);
    addEdge(adj, 2, 8, 2);
    addEdge(adj, 2, 5, 4);
    addEdge(adj, 3, 4, 9);
    addEdge(adj, 3, 5, 14);
    addEdge(adj, 4, 5, 10);
    addEdge(adj, 5, 6, 2);
    addEdge(adj, 6, 7, 1);
    addEdge(adj, 6, 8, 6);
    addEdge(adj, 7, 8, 7);
    shortestPath(adj, V, 0);
    return 0;
}
````
````java
// Java program for the above approach
import java.util.*;
class GFG {
    private static final int INF = 0x3f3f3f3f;
    // To add an edge
    static void
    addEdge(List<List<Pair<Integer, Integer> > > adj, int u,
            int v, int wt)
    {
        adj.get(u).add(new Pair<>(v, wt));
        adj.get(v).add(new Pair<>(u, wt));
    }
    // Prints shortest paths from src to all other vertices
    static void
    shortestPath(List<List<Pair<Integer, Integer> > > adj,
                 int V, int src)
    {
        // Create a priority queue to store vertices that
        // are being preprocessed.
        PriorityQueue<Pair<Integer, Integer> > pq
            = new PriorityQueue<>(
                Comparator.comparingInt(Pair::getFirst));
        // Create a list for distances and initialize all
        // distances as infinite (INF)
        List<Integer> dist
            = new ArrayList<>(Collections.nCopies(V, INF));
        // Insert source itself in priority queue and
        // initialize its distance as 0.
        pq.add(new Pair<>(0, src));
        dist.set(src, 0);
        /* Looping till priority queue becomes empty (or all
        distances are not finalized) */
        while (!pq.isEmpty()) {
            // The first vertex in pair is the minimum
            // distance vertex, extract it from priority
            // queue.
            int u = pq.peek().getSecond();
            pq.poll();
            // Get all adjacent of u.
            for (Pair<Integer, Integer> x : adj.get(u)) {
                // Get vertex label and weight of current
                // adjacent of u.
                int v = x.getFirst();
                int weight = x.getSecond();
                // If there is a shorter path to v through
                // u.
                if (dist.get(v) > dist.get(u) + weight) {
                    // Updating distance of v
                    dist.set(v, dist.get(u) + weight);
                    pq.add(new Pair<>(dist.get(v), v));
                }
            }
        }
        // Print shortest distances stored in dist[]
        System.out.println("Vertex \tDistance from Source");
        for (int i = 0; i < V; i++) {
            System.out.printf("%d \t\t %d\n", i,
                              dist.get(i));
        }
    }
    // Driver program to test methods of graph class
    public static void main(String[] args)
    {
        int V = 9;
        List<List<Pair<Integer, Integer> > > adj
            = new ArrayList<>(V);
        for (int i = 0; i < V; i++) {
            adj.add(new ArrayList<>());
        }
        // Making the above-shown graph
        addEdge(adj, 0, 1, 4);
        addEdge(adj, 0, 7, 8);
        addEdge(adj, 1, 2, 8);
        addEdge(adj, 1, 7, 11);
        addEdge(adj, 2, 3, 7);
        addEdge(adj, 2, 8, 2);
        addEdge(adj, 2, 5, 4);
        addEdge(adj, 3, 4, 9);
        addEdge(adj, 3, 5, 14);
        addEdge(adj, 4, 5, 10);
        addEdge(adj, 5, 6, 2);
        addEdge(adj, 6, 7, 1);
        addEdge(adj, 6, 8, 6);
        addEdge(adj, 7, 8, 7);
        shortestPath(adj, V, 0);
    }
}
class Pair<T, U> {
    private T first;
    private U second;
    public Pair(T first, U second)
    {
        this.first = first;
        this.second = second;
    }
    public T getFirst() { return first; }
    public U getSecond() { return second; }
}
````
````python3
import heapq
# Function to add an edge to the adjacency list
def addEdge(adj, u, v, wt):
    adj[u].append((v, wt))
    adj[v].append((u, wt))
# Function to find the shortest paths from source to all other vertices
def shortestPath(adj, V, src):
    # Create a priority queue to store vertices that are being preprocessed
    pq = []
    # Create an array for distances and initialize all distances as infinite (INF)
    dist = [float('inf')] * V
    # Insert source itself in the priority queue and initialize its distance as 0
    heapq.heappush(pq, (0, src))
    dist[src] = 0
    # Loop until the priority queue becomes empty
    while pq:
        # Extract the vertex with minimum
        # distance from the priority queue
        distance, u = heapq.heappop(pq)
        # Get all adjacent vertices of u
        for v, weight in adj[u]:
            # If there is a shorter path to v through u
            if dist[v] > dist[u] + weight:
                # Update distance of v
                dist[v] = dist[u] + weight
                heapq.heappush(pq, (dist[v], v))
    # Print shortest distances stored in dist[]
    print("Vertex Distance from Source")
    for i in range(V):
        print(i,"    ",dist[i])
# Main function
if __name__ == "__main__":
    V = 9
    adj = [[] for _ in range(V)]
    # Making the graph
    addEdge(adj, 0, 1, 4)
    addEdge(adj, 0, 7, 8)
    addEdge(adj, 1, 2, 8)
    addEdge(adj, 1, 7, 11)
    addEdge(adj, 2, 3, 7)
    addEdge(adj, 2, 8, 2)
    addEdge(adj, 2, 5, 4)
    addEdge(adj, 3, 4, 9)
    addEdge(adj, 3, 5, 14)
    addEdge(adj, 4, 5, 10)
    addEdge(adj, 5, 6, 2)
    addEdge(adj, 6, 7, 1)
    addEdge(adj, 6, 8, 6)
    addEdge(adj, 7, 8, 7)
    # Finding shortest paths from source vertex 0
    shortestPath(adj, V, 0)
````
````csharp
using System;
using System.Collections.Generic;
class GFG {
    // To add an edge
    static void AddEdge(List<List<int[]>> adj, int u, int v, int wt) {
        adj[u].Add(new int[] { v, wt });
        adj[v].Add(new int[] { u, wt });
    }
    // Dijkstra's Algorithm Implementation
    static void ShortestPath(List<List<int[]>> adj, int V, int src) {
        // Min-Heap Priority Queue
        MinHeap pq = new MinHeap(V);
        // Distance array, initialize with INF
        int[] dist = new int[V];
        for (int i = 0; i < V; i++) {
            dist[i] = int.MaxValue;
        }
        // Start from the source
        dist[src] = 0;
        pq.Push(src, 0);
        while (!pq.IsEmpty()) {
            int[] top = pq.Pop();
            int u = top[0];
            int currentDist = top[1];
            // Process all neighbors of u
            foreach (var neighbor in adj[u]) {
                int v = neighbor[0];
                int weight = neighbor[1];
                if (currentDist + weight < dist[v]) {
                    dist[v] = currentDist + weight;
                    pq.Push(v, dist[v]);
                }
            }
        }
        // Print shortest distances from the source
        Console.WriteLine("Vertex \t Distance from Source");
        for (int i = 0; i < V; i++) {
            Console.WriteLine($"{i}\t\t {dist[i]}");
        }
    }
    public static void Main(string[] args) {
        int V = 9;
        var adj = new List<List<int[]>>(V);
        for (int i = 0; i < V; i++) {
            adj.Add(new List<int[]>());
        }
        // Graph edges
        AddEdge(adj, 0, 1, 4);
        AddEdge(adj, 0, 7, 8);
        AddEdge(adj, 1, 2, 8);
        AddEdge(adj, 1, 7, 11);
        AddEdge(adj, 2, 3, 7);
        AddEdge(adj, 2, 8, 2);
        AddEdge(adj, 2, 5, 4);
        AddEdge(adj, 3, 4, 9);
        AddEdge(adj, 3, 5, 14);
        AddEdge(adj, 4, 5, 10);
        AddEdge(adj, 5, 6, 2);
        AddEdge(adj, 6, 7, 1);
        AddEdge(adj, 6, 8, 6);
        AddEdge(adj, 7, 8, 7);
        ShortestPath(adj, V, 0);
    }
}
// Custom Min-Heap (Priority Queue) Implementation
class MinHeap {
    private int[][] heap;
    private int size;
    public MinHeap(int capacity) {
        heap = new int[capacity][];
        size = 0;
    }
    public void Push(int node, int priority) {
        heap[size] = new int[] { node, priority };
        int current = size;
        size++;
        // Bubble up
        while (current > 0) {
            int parent = (current - 1) / 2;
            if (heap[current][1] >= heap[parent][1]) break;
            int[] temp = heap[current];
            heap[current] = heap[parent];
            heap[parent] = temp;
            current = parent;
        }
    }
    public int[] Pop() {
        if (size == 0) throw new InvalidOperationException("Heap is empty.");
        int[] min = heap[0];
        heap[0] = heap[size - 1];
        size--;
        // Bubble down
        int current = 0;
        while (true) {
            int left = 2 * current + 1;
            int right = 2 * current + 2;
            int smallest = current;
            if (left < size && heap[left][1] < heap[smallest][1]) {
                smallest = left;
            }
            if (right < size && heap[right][1] < heap[smallest][1]) {
                smallest = right;
            }
            if (smallest == current) break;
            int[] temp = heap[current];
            heap[current] = heap[smallest];
            heap[smallest] = temp;
            current = smallest;
        }
        return min;
    }
    public bool IsEmpty() {
        return size == 0;
    }
}
````
**Output**
```
Vertex 	Distance from Source
0 		 0
1 		 4
2 		 12
3 		 19
4 		 21
5 		 11
6 		 9
7 		 8
8 		 14
```
**Time Complexity:**  O(E\*logV), Where E is the number of edges and V is the number of vertices.
 **Auxiliary Space:**  O(V), Where V is the number of vertices.
**Notes:** 
1. The code calculates the shortest distance but doesn’t calculate the path information. We can create a parent array, update the parent array when distance is updated (like [prim’s implementation](https://www.geeksforgeeks.org/dsa/prims-mst-for-adjacency-list-representation-greedy-algo-6/)), and use it to show the shortest path from the source to different vertices.
2. The code is for undirected graphs, same Dijkstra function can be used for directed graphs also.
3. The code finds the shortest distances from the source to all vertices. If we are interested only in the shortest distance from the source to a single target, we can break the for loop when the picked minimum distance vertex is equal to the target (Step 3 of the algorithm).
4. Dijkstra’s algorithm doesn't work for graphs with negative weight edges. For graphs with negative weight edges, the [Bellman-Ford algorithm](https://www.geeksforgeeks.org/dsa/bellman-ford-algorithm-dp-23/) can be used.
**Related Articles**:
[Printing Paths in Dijkstra’s Shortest Path Algorithm](https://www.geeksforgeeks.org/dsa/printing-paths-dijkstras-shortest-path-algorithm/) 
[Dijkstra’s shortest path algorithm using a set in STL](https://www.geeksforgeeks.org/dsa/dijkstras-shortest-path-algorithm-using-set-in-stl/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dsa/dijkstras-algorithm-for-adjacency-list-representation-greedy-algo-8/)

## GATE CS

- Subject: Algorithms
- Topic: Greedy Techniques

> [!note] Related notes
>
> - [[Efficient Huffman Coding for Sorted Input]]
> - [[Fractional Knapsack Problem]]
> - [[Introduction to Greedy Algorithms]]
> - [[Optimal File Merge Patterns]]
> - [[Prim’s Minimum Spanning Tree]]
> - [[Prim’s MST for Adjacency List Representation]]
> - [[Applications of Depth First Search]]
> - [[Asymptotic Notations]]
> - [[Binary Search]]
> - [[Breadth First Traversal or BFS for a Graph]]

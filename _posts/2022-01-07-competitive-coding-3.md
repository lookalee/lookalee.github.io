---
layout: single
title: "[Algorithms] Depth-First-Search and Breadth-First-Search"
tags: [algorithms]
categories: algorithm


---

# Depth-First-Search (DFS) and Breadth-First-Search (BFS)

- DFS is preferred if we just want to visit every node in the graph, since it is simpler. 

- BFS if preferred is we want to find the path between two nodes (ex: finding path of friendships between two people).

- Pseudocode for DFS (uses recursion): 

  ```c++
  void search(Node root) {
      if (root == null) return;
      visit(root);
      root.visited = true;
      for each (Node n in root.adjacent) {
          if (n.visited == false) {
              search(n);
          }
      }
  }
  ```

  

- Pseudocode for BFS (uses queue):

```c++
void search(Node root) {
    Queue queue = new Queue();
    root.marked = true;
    queue.enqueue(root); //Add to end
    while(!queue.isEmpty()) {
        Node r = queue.dequeue(); //Remove from front
        visit(r);
        for each(Node n in r.adjacent) {
            if (n.makred == false) {
                n.marked = true;
                queue.enqueue(n);
            }
        }
    }
}
```

### Bidirectional Search

- Bidirectional serach can be used to find the shortest path between two nodes. 
- Operates essentially by **running two BFS**, one from each node.
- Has faster run-time than a BFS, as O(k^d) is reduced to O(k^(d/2))
# Depth First Search(DFS)

![DFS](https://github.com/alrightchiu/SecondRound/blob/master/content/Algorithms%20and%20Data%20Structures/Graph%20series/DFS_fig/f_2.png?raw=true)

If we use DFS start with vertex(A), we could get:
  * As long as there's at least one path between vertex and vertex(A) in Graph, **DFS can find one of the paths, but the path might not be the shortest path.**

## Algorithms

Items in DFS:
* **time**: There's a timeline with 2N time-points on it, where N stands for number of vertexes in Graph.
* **discover** and **finish** array: the two time-points assigned to each vertex.
  * **discover**: If vertex(B) is found be vertex(A), the discover[B] == discover[A] + 1; which means in the whole timeline, vertex(B) is found after vertex(A).
  * **finish**: All paths, start from vertex(B), are explored, and all possible vertexes are found, we can say the exploration start from vertex(B) finished, and mark as finish[B]
* **color** array: Vertexes are marked with colors to identify discovered and finished.
  * **white**: Not discovered yet.
  * **gray**: Discovered and not finished yet.
  * **black**: Finished.
* **predecessor** array: To record the vertexes exploration relation, so we can found path, as BFS, DFS can generate a predecessor sub graph.

Time Stamp example:
![time stamp](https://github.com/alrightchiu/SecondRound/blob/master/content/Algorithms%20and%20Data%20Structures/Graph%20series/DFS_fig/f_18.png?raw=true)

# Graph
refs: http://alrightchiu.github.io/SecondRound/graph-introjian-jie.html
Graph is a model to keep the relation between data.

* **Vertex**: Every data node is a **vertex**, and the set of all vertexes is called **V** or **V(G)**

* **Edge**: Every line/arrow between a pair of vertext is called **edge**, marked as (Vi, Vj). the set of all edges is called E or E(G).

Graph is defined as the set consist of V and E, marked as G(V, E).


* Directed graph: The direction of edge represents the relation between vertexes. If it is unidirectional relation between vertex A and B, that means there's directionality relation between vertex A and B.

* Undirected graph: The direction of edge represents the relation between vertexes. If it's two-way  relation between vertex A and B, that means there's directionality relation between vertex A and B.

### Problems
Q: Give an algorithm that determines whether or not a given undirected graph G=(V, E)contains a cycle. Your algorithm should run in O(|V|) time, independent of |E|

An undirected graph is acyclic if and only if there is no back edges.
  * If there's a back edge, there's a cycle.
  * If there's no back edge, there are only tree edges, thus there's no cycle.

Thus, we can run DFS: if we find a back edge, there's a cycle.
  * Time: O(V). If we ever seen |V| distinct edges, we must have seen a back edge, since in a acyclic forest, |E| <= |V| - 1

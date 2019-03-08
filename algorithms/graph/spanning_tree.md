# Spanning Tree

A **spanning tree** is a subset of Graph G, which has all the vertices covered with minimum possible number of edges.

In a weighted graph, a **minimum spanning tree** is a spanning tree which has less weight than all other spanning trees of the same graph.

Two popular algorithms: **Kruskal's algorithm** & **Prim's algorithm**

|    **Kruskal's algorithm**    |    **Prim's algorithm**    |
|-------------------------------|----------------------------|
|  Shortest edge without cycle  |  Nearest vertex not added  |
|        O(E log V) time        |   O(E logV) time<br/>can be improved using Fibonacci Heaps to O(E + logV)|
| Performs better in typical situations (sparse graphs) because it uses simpler data structures. | significantly faster in the limit when you've got a really dense graph with many more edges than vertices.|

**Use Prim's algorithm when you have a graph with lots of edges else use Kruskal’s algorithm.**

![Kruskal Algorithm](https://qph.fs.quoracdn.net/main-qimg-236c1de206e8d21c168dfc21998778d4)

![Prim's Algorithm](https://qph.fs.quoracdn.net/main-qimg-4a0ea6431c993b42362b3f26e9a4ed65)

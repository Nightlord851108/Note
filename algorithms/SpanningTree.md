# Spanning tree
A spanning tree is a subset of Graph G, which has all the vertices covered with minimum possible number of edges.

In a weighted graph, a minimum spanning tree is a spanning tree that has minimum weight than all other spanning trees of the same graph.


**Use Prim's algorithm when you have a graph with lots of edges else use Kruskal’s algorithm.**
## Kruskal's algorithm
Kruskal's algorithm can be shown to run in O(E log E) time, or equivalently, O(E log V) time, where E is the number of edges in the graph and V is the number of vertices, all with simple data structures.

Kruskal’s Algorithm performs better in typical situations (sparse graphs) because it uses simpler data structures.

![Kurskal's algorithm](https://qph.fs.quoracdn.net/main-qimg-236c1de206e8d21c168dfc21998778d4)

## Prim's algorithm
The time complexity is O(VlogV + ElogV) = O(ElogV), making it the same as Kruskal's algorithm. However, Prim's algorithm can be improved using Fibonacci Heaps to O(E + logV).

Prim's Algorithm : is significantly faster in the limit when you've got a really dense graph with many **more edges than vertices**.

![Prim's algorithm](https://qph.fs.quoracdn.net/main-qimg-4a0ea6431c993b42362b3f26e9a4ed65)

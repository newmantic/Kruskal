# Kruskal


Kruskal's Algorithm is an algorithm ti find Minimum Spanning Tree (MST). Given a connected, undirected graph G = (V, E) with weights w(u, v) for each edge (u, v) in E, a minimum spanning tree is a subset of edges that connects all vertices without cycles and has the minimum possible total edge weight.


Initialization:
Create a list of all edges in the graph G.
Sort the edges in non-decreasing order based on their weights:
edges.sort(key=lambda x: x[2]) // where x = (u, v, weight)

Create Disjoint Sets:
Initialize a disjoint-set data structure (or union-find) to manage connected components.
Each vertex is initially in its own set.

Initialize an empty list MST to store the edges of the minimum spanning tree.
Initialize total_weight = 0 to keep track of the total weight of the MST.
For each edge (u, v, weight) in the sorted list:
Check if u and v belong to different sets:
If find(u) != find(v): // Check if they are in different components
Add the edge (u, v) to the MST:
MST.append((u, v, weight))
Update the total weight:
total_weight += weight
Union the sets of u and v:
union(u, v)

Termination:
The algorithm terminates when we have added |V| - 1 edges to the MST, where |V| is the number of vertices.

Time Complexity:
The time complexity of Kruskal's algorithm is O(E log E) for sorting the edges, plus O(E α(V)) for union-find operations, where α is the inverse Ackermann function.


Kruskal's algorithm is greedy; it always selects the smallest edge that connects two different components.
It is particularly efficient for sparse graphs.


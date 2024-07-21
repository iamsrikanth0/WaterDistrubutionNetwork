# WaterDistrubutionNetwork
To design a water distribution network for selected areas in Hyderabad using graphs and Prim's algorithm to find the Minimum Spanning Tree (MST) that minimizes the cost of connecting all areas.

Approach:
Graph Representation:
   - Define a class "Edge" to represent connections between areas ("src" and "dest") with associated weights (costs).
   - Use a map-like structure to represent the graph where each area (node) connects to others through edges.
Prim's Algorithm Implementation:
   - Initialize with a starting area (node).
   - Use two sets: "MSTSet" (to store vertices included in MST) and "nonMSTSet" (to manage the priority queue for non-MST vertices).
   - Use a priority queue (min-heap) to always extend the MST with the cheapest edge.
   - Maintain a `visited` array (boolean) to track included vertices.
Steps:
   - Start with an arbitrary vertex (or chosen strategically based on requirements).
   - Add this vertex to the MSTSet and add its edges to the priority queue.
   - Repeat until all vertices are in the MSTSet:
     - Extract the minimum weight edge from the priority queue.
     - If the destination vertex of the edge is not in MSTSet, add it to MSTSet and add its edges to the priority queue.
   - Compute the total cost of the MST.
Java Code Implementation:
   - Define classes for "Edge", "Area", and "HyderabadWaterNetwork".
   - Implement Prim's algorithm in the "HyderabadWaterNetwork" class to find the MST.


Explanation:
- Area Class: Represents an area in Hyderabad.
- Edge Class: Represents a pipe (connection) between two areas with a weight (cost).
- HyderabadWaterNetwork Class: Manages areas and edges, implements Prim's algorithm to find the MST representing the water distribution network.
- Main Class ("HyderabadWaterDistribution"): Initializes the network, adds areas and pipes, and computes the MST cost using the "primMST" method of the "HyderabadWaterNetwork" class.

Algorithm explanation:
- What is MST? 1. Includes all Nodes 2. Min edge weight 3. No cycle (that is why it is called Tree)--->> Only for Undirected graphs
We use prim's algo- MST set and Non MST set, here we will start with one starting point, Node, push it to MST set, now we will check which one has low weight and then start pushing the second one. We will check all the neighbours whose cost/wt is low , then push to MST. This is the approach.
So here we are expecting to get min wt node, this can be done by Priority Queue. There in Code, our Non MST is nothing but a priority Queue. Role of MST set is done by Visited array
Worst Case- we will have to add all the edges, so O(ElogE)

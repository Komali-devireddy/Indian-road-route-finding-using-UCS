# 🇮🇳 India Route Finding Using Uniform Cost Search (UCS)

## Project Title
**India Route Finding Using Uniform Cost Search (UCS)**

## Project Description
This project implements **Uniform Cost Search (UCS)** to find the least-cost route between cities in India.

The Indian road network is represented as a weighted graph:
- Cities are nodes.
- Roads are edges.
- Road distances are edge costs.
- UCS selects the path with the lowest accumulated cost.

## Objectives
1. Represent Indian cities and roads as a weighted graph.
2. Implement Uniform Cost Search.
3. Find the minimum-cost route between two cities.
4. Calculate total route distance.
5. Display the optimal route.
6. Visualize the road network.
7. Understand UCS in a real-world navigation problem.

## What is Uniform Cost Search?
Uniform Cost Search is an uninformed search algorithm that always expands the node with the **lowest path cost**.

**Total Cost = Sum of all road/edge costs travelled so far**

Example:

```text
A → B = 100 km
A → C = 50 km
C → B = 20 km
```

Routes:

```text
A → B
Cost = 100 km

A → C → B
Cost = 50 + 20 = 70 km
```

UCS selects `A → C → B` because its total cost is lower.

## Problem Representation

```text
Nodes   → Indian Cities
Edges   → Roads connecting cities
Weights → Road distances
```

The road network is therefore a **weighted graph**.

## Working of UCS

1. Select a source city.
2. Select a destination city.
3. Insert the source into a priority queue with cost 0.
4. Remove the city having the smallest accumulated cost.
5. Explore its neighbouring cities.
6. Calculate the new path cost.
7. Update the priority queue when a cheaper path is found.
8. Continue until the destination is reached.
9. Reconstruct the route using parent information.
10. Display the route and total distance.

### UCS Pseudocode

```text
UCS(Graph, Start, Goal)

1. Create a priority queue.
2. Insert Start with cost 0.
3. Set Start as having no parent.
4. While the queue is not empty:
      Remove the node with minimum cost.
      If node is Goal:
          Stop.
      For every neighbour:
          Calculate new path cost.
          If new cost is smaller:
              Update cost.
              Store parent.
              Add neighbour to queue.
5. Reconstruct the path.
6. Return route and total cost.
```

## Technologies Used

- Python
- Google Colab / Jupyter Notebook
- Pandas
- Matplotlib
- NetworkX
- Heapq

## Project Structure

```text
India-UCS-Route-Finding/
│
├── India_UCS_Route_Finding.ipynb
├── README.md
├── indian_cities_dataset.csv
└── visualizations/
```

## Dataset

The dataset contains information about Indian cities and road connections.

Typical attributes:

| Attribute | Description |
|---|---|
| Source | Starting/connected city |
| Destination | Connected city |
| Distance | Road distance |
| Cost | Weight used by UCS |

The road distance acts as the edge weight.

## Graph Visualization

The road network can be visualized using NetworkX and Matplotlib.

Example:

```text
             Delhi
            /     \\
           /       \\
     Jaipur         Lucknow
       |               |
   Ahmedabad         Patna
       |               |
     Mumbai -------- Hyderabad
                       |
                   Bengaluru
                       |
                    Chennai
```

The visualization helps show city connections, possible routes, and the selected route.

## Route Finding Example

Example:

```text
Source      : Hyderabad
Destination : Chennai

Optimal Route:
Hyderabad → Bengaluru → Chennai

Total Distance:
Approximately 630 km
```

**Note:** The actual route and distance depend on the dataset used.

## Why UCS is Used

UCS is appropriate because:
- Different roads have different distances.
- The objective is to minimize total travel distance.
- It considers accumulated path cost.
- It provides an optimal solution for non-negative edge costs.
- It is more suitable than BFS for weighted road networks.

## UCS vs BFS

| Feature | BFS | UCS |
|---|---|---|
| Edge Cost | Equal-cost assumption | Different costs supported |
| Data Structure | Queue | Priority Queue |
| Selection | Shallowest node | Lowest-cost node |
| Weighted graph | Not necessarily optimal | Optimal for non-negative costs |
| Route planning | Limited | Suitable |

## Complexity

For branching factor `b`, optimal solution cost `C*`, and minimum step cost `ε`:

```text
Time Complexity:
O(b^(1 + floor(C*/ε)))
```

UCS can require significant memory because generated nodes are stored in the priority queue.

## Advantages

1. Finds a minimum-cost path.
2. Supports different edge weights.
3. Complete when step costs are positive.
4. Optimal for non-negative edge costs.
5. Uses a simple priority-queue strategy.
6. Useful for route-planning problems.

## Limitations

1. Can consume considerable memory.
2. May explore many routes.
3. Can be slow for very large graphs.
4. Does not use geographical heuristics.
5. Performance depends on graph size and connectivity.

## Real-World Applications

- GPS route planning
- Navigation systems
- Logistics and delivery planning
- Transportation planning
- Emergency vehicle routing
- Robot navigation
- Railway route planning
- Supply-chain optimization

## Experimental Procedure

1. Load the Indian city/road dataset.
2. Inspect and clean the data.
3. Create a weighted graph.
4. Add cities as nodes.
5. Add roads as weighted edges.
6. Select source and destination.
7. Initialize the UCS priority queue.
8. Explore nodes according to cumulative cost.
9. Store parent information.
10. Continue until the destination is reached.
11. Reconstruct the optimal path.
12. Calculate total distance.
13. Display the result.
14. Generate graph visualization.
15. Highlight the selected route where implemented.

## Expected Output

```text
====================================
 INDIA ROUTE FINDING USING UCS
====================================

Source City      : Hyderabad
Destination City : Chennai

Optimal Route:
Hyderabad → Bengaluru → Chennai

Total Distance:
XXXX km

Search Completed Successfully.
```

The exact result depends on the dataset and selected cities.

## Measures of Evaluation

### 1. Total Path Cost
```text
Path Cost = Σ Road Distances
```

### 2. Nodes Explored
Number of cities expanded during the search.

### 3. Nodes Generated
Number of possible states created during the search.

### 4. Execution Time
Time required to find the route.

### 5. Path Length
Number of cities/edges in the final route.

## Learning Outcomes

After completing this project, the learner should be able to:
- Understand weighted graph problems.
- Understand Uniform Cost Search.
- Implement a priority queue.
- Represent road networks as graphs.
- Find minimum-cost routes.
- Analyze search performance.
- Visualize graph-based problems.
- Apply AI search algorithms to navigation.

## Conclusion

This project demonstrates how **Uniform Cost Search can be applied to an Indian road network to find a minimum-cost route between two cities**.

Cities are represented as nodes and road distances as weighted edges. UCS always selects the currently cheapest accumulated path, making it suitable for weighted route-finding problems.

The experiment provides a practical example of applying an **Artificial Intelligence search technique to a real-world navigation problem**.

## How to Run the Project

### Step 1 — Open Google Colab
Open `India_UCS_Route_Finding.ipynb` in Google Colab.

### Step 2 — Upload Dataset
Upload the required Indian cities/roads CSV file.

### Step 3 — Run the Notebook
Run the cells from top to bottom.

### Step 4 — Select Cities
Provide valid source and destination cities.

Example:

```text
Source      : Hyderabad
Destination : Chennai
```

### Step 5 — View Results
The notebook displays:
- Optimal route
- Total distance
- Search results
- Graph visualization

## Troubleshooting

### FileNotFoundError
Make sure the CSV file is uploaded to Colab and the filename matches the code.

### NameError: pd is not defined

```python
import pandas as pd
```

### NameError: nx is not defined

```python
import networkx as nx
```

### NameError: plt is not defined

```python
import matplotlib.pyplot as plt
```

### NameError: heapq is not defined

```python
import heapq
```

## Project Summary

| Item | Description |
|---|---|
| Problem | Indian Route Finding |
| Algorithm | Uniform Cost Search |
| Graph Type | Weighted Graph |
| Node | City |
| Edge | Road |
| Edge Weight | Distance |
| Objective | Minimum-cost route |
| Language | Python |
| Platform | Google Colab |
| Visualization | NetworkX + Matplotlib |
| Search Structure | Priority Queue |

## Keywords

`Uniform Cost Search` · `UCS` · `Artificial Intelligence` · `Graph Search` · `Shortest Path` · `Route Finding` · `Indian Roads` · `Weighted Graph` · `Priority Queue` · `Python` · `Google Colab` · `NetworkX`

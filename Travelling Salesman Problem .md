# Ex. No: 18D - Travelling Salesman Problem (TSP)

## AIM:
To write a Python program to find the shortest possible route that visits every city exactly once and returns to the starting point using the **Travelling Salesman Problem (TSP)** approach.

## ALGORITHM:

**Step 1**: Start the program.

**Step 2**: Input the number of cities and the distance matrix.

**Step 3**: Set the starting city (e.g., city `0`).

**Step 4**: Generate all possible permutations of the remaining cities.

**Step 5**: For each permutation:
- Calculate the total cost of traveling through the permutation starting and ending at city `0`.
- Keep track of the **minimum cost** and the corresponding route.

**Step 6**: Return the **route** and the **minimum cost**.

**Step 7**: End the program.

## PYTHON PROGRAM

```
from sys import maxsize
from itertools import permutations

V = 4

# Implementation of Traveling Salesman Problem
def travellingSalesmanProblem(graph, s):
    # Store all vertices except the starting vertex
    vertex = []
    for i in range(V):
        if i != s:
            vertex.append(i)

    # Store minimum weight Hamiltonian Cycle
    min_path = maxsize

    # Generate all permutations of the vertex list
    for perm in permutations(vertex):
        # Store current path weight (cost)
        current_pathweight = 0

        # Compute current path weight
        k = s
        for j in perm:
            current_pathweight += graph[k][j]
            k = j
        current_pathweight += graph[k][s]  # return to start

        # Update minimum
        min_path = min(min_path, current_pathweight)

    return min_path

# Driver Code
if __name__ == "__main__":
    graph = [[0, 10, 15, 20],
             [10, 0, 35, 25],
             [15, 35, 0, 30],
             [20, 25, 30, 0]]

    s = int(input())
    print(travellingSalesmanProblem(graph, s))

```

## OUTPUT

![image](https://github.com/user-attachments/assets/c7011366-cbfc-4c2c-ac7b-570c21ebb78f)


## RESULT

Thus the python program was written and executed successfully.


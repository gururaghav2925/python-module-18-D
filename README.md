# Travelling Salesman Problem (TSP) using Python

# Aim
To implement a solution for the Travelling Salesman Problem (TSP) in Python, which finds the shortest possible route that visits each city exactly once and returns to the starting city.

# Procedure
1. Understand the Travelling Salesman Problem (TSP) as a combinatorial optimization problem.
2. Represent the cities and distances between them using a distance matrix or adjacency list.
3. Choose an appropriate algorithm for solving TSP (e.g., brute-force, dynamic programming with bitmasking, or approximate methods like greedy or nearest neighbor).
4. If using brute-force:
   - Generate all permutations of the cities.
   - Calculate the total distance for each possible route that visits all cities and returns to the start.
   - Track and return the route with the minimum total distance.
5. If using dynamic programming:
   - Use a recursive approach with memoization to avoid recalculating overlapping subproblems.
6. Return the optimal route and its total cost (minimum distance).
7. Display the result: the shortest path covering all cities and the corresponding distance.
# Program
```python
# Python3 program to implement traveling salesman
# problem using naive approach.
from sys import maxsize
from itertools import permutations
V = 4

# implementation of traveling Salesman Problem
def travellingSalesmanProblem(graph, s):

	# store all vertex apart from source vertex
	vertex = []
	for i in range(V):
		if i != s:
			vertex.append(i)

	# store minimum weight Hamiltonian Cycle
	min_path = maxsize
	next_permutation=permutations(vertex)
	for i in next_permutation:

		# store current Path weight(cost)
		current_pathweight = 0

		# compute current path weight
		k = s
		for j in i:
			current_pathweight += graph[k][j]
			k = j
		current_pathweight += graph[k][s]

		# update minimum
		min_path = min(min_path, current_pathweight)
		
	return min_path

# Driver Code
if __name__ == "__main__":

	# matrix representation of graph
	graph = [[0, 10, 15, 20], [10, 0, 35, 25],
			[15, 35, 0, 30], [20, 25, 30, 0]]
	s = int(input())
	print(travellingSalesmanProblem(graph, s))
```

# Output


![image](https://github.com/user-attachments/assets/11b675a9-d883-467a-9503-b6b41b815d29)

# Result
The Travelling Salesman Problem is successfully implemented using Python. The program calculates the shortest possible route that visits every city exactly once and returns to the starting city, along with the total minimum distance of that route.

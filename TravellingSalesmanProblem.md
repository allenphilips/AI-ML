from sys import maxsize<br>
from itertools import permutations<br>
V = 4<br>
def travellingSalesmanProblem(graph, s):<br>
<br>
 vertex = []<br>
 for i in range(V):<br>
 if i != s:<br>
 vertex.append(i)<br>
 <br>
 min_path = maxsize<br>
 next_permutation=permutations(vertex)<br>
 for i in next_permutation:<br>
 <br>
 current_pathweight = 0<br>
 <br>
 k = s<br>
 for j in i:<br>
 current_pathweight += graph[k][j]<br>
 k = j<br>
 current_pathweight += graph[k][s]<br>
 <br>
 min_path = min(min_path, current_pathweight)<br>
 return min_path<br>

if __name__ == "__main__":<br>
 graph = [[0, 10, 15, 20], [10, 0, 35, 25],<br>
 [15, 35, 0, 30], [20, 25, 30, 0]]<br>
 s = 0<br>
 print(travellingSalesmanProblem(graph, s))<br><br>
Output:<br>
80<br>

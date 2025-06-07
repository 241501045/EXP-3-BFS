# EXP-3-BFS
from collections import deque

def bfs(graph, start, goal):
    queue = deque([(start, [start])])
    visited = set()

   while queue:
        (vertex, path) = queue.popleft()
        if vertex in visited:
            continue
        visited.add(vertex)

   if vertex == goal:
            return path  # Return the path from start to goal

   for neighbor in graph.get(vertex, []):
            if neighbor not in visited:
                queue.append((neighbor, path + [neighbor]))

  return None  # No path found


def degrees_AdjMatrix(graph):
    vertices = sorted(graph)
    n = len(vertices)
    adj = [[0] * n for _ in range(n)]
    indegree, outdegree = {v:0 for v in vertices}, {v:0 for v in vertices}

    for i,v in enumerate(vertices):
        outdegree[v] = len(graph[v])
        for u in graph[v]:
            adj[i][vertices.index(u)] = 1
            indegree[u] += 1
    
    print(f"Indegree : {indegree}\nOutdegree : {outdegree}\nAdjacent Matrix : ")
    for row in adj:
        print(row)

graph = {
    'A':['B','C'],
    'B':['D'],
    'C':['D'],
    'D':[]
}
degrees_AdjMatrix(graph)
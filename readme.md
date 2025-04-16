#kruskal's algo
def find(parent, i):
    if parent[i] != i:
        parent[i] = find(parent, parent[i])
    return parent[i]

def union(parent, rank, x, y):
    rootX, rootY = find(parent,x), find(parent, y)
    if rank[rootX] > rank[rootY]:
        parent[rootY] = rootX

    elif rank[rootX] < rank[rootY]:
        parent[rootX] = rootY

    else:
        parent[rootY] = rootX
        rank[rootX] += 1

def kruskal(graph):
    mst = []
    edges = sorted(graph, key=lambda x:x[2])
    parent, rank = {}, {}

    for u,v,w in edges:
        parent.setdefault(u,u)
        parent.setdefault(v,v)
        rank.setdefault(u,0)
        rank.setdefault(v,0)
    
    for u,v,w in edges:
        if find(parent,u) != find(parent,v):
            union(parent,rank,u,v)
            mst.append((u,v,w))
    return mst

graph = [ (0,1,10), (0,2,6), (0,3,5), (1,3,15), (2,3,4) ]
mst = kruskal(graph)
print("MST edges : ",mst)
#kruskallllllllllllllll mmmmmmmm
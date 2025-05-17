# Deleted

def optimalBst(keys, freq):
    n = len(keys)
    cost = [[0] * n for _ in range(n)]

    for i in range(n):
        cost[i][i] = freq[i]

    for length in range(2, n+1):
        for i in range(n-length+1):
            j = n-length+1
            cost[i][j] = float('inf')
            for r in range(i, j+1):
                c = (cost[i][r-1] if r>i else 0) + (cost[r+1][j] if r<j else 0) + sum(freq[i:j + 1])
                if c<cost[i][j]:
                    cost[i][j] = c
    return cost[0][n-1]

keys = [10,20,30,40]
freq = [4,2,6,3]
print("Optimal Cost : ",optimalBst(keys, freq))
#haaaaaaaaaaaaaaaaaaaaa ahaaaaahhhhhhhhhhhh

def selectionSort(arr):
    n = len(arr)
    for i in range(n):
        minInx = min(range(i,n), key = arr.__getitem__)
        arr[i], arr[minInx] = arr[minInx], arr[i]

arr = [64,25,12,22,11]
selectionSort(arr)
print("sorted array : ",arr) 
#dfghjk yeahhhhhhhhhh ngrok ki JAI HOooooooooo
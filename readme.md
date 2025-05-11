def qs(arr):
    n = len(arr)
    if n<=1: 
        return arr
    
    pivot = arr[n//2]
    return qs([x for x in arr if x<pivot]) + [x for x in arr if x==pivot] + qs([x for x in arr if x>pivot])

arr = [64,25,12,22,11]
print("Sorted array : ",qs(arr))

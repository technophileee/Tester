def qs(arr):
    n = len(arr)
    if n<=1: 
        return arr
    
    pivot = arr[n//2]
    return qs([x for x in arr if x<pivot]) + [x for x in arr if x==pivot] + qs([x for x in arr if x>pivot])

arr = [0,0,0,0,0]
for i in range(0,5):
  x=int(input())
  arr[i]=x

print("Sorted array : ",qs(arr))

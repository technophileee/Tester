def ms(arr):
    n = len(arr)
    if n<=1:
        return arr
    
    mid = n//2
    left  = ms(arr[:mid])
    right =  ms(arr[mid:])
    return sorted(left + right)

arr = [64,25,22,12,11]
print("Sorted array : ", ms(arr))
number = int(input("Enter number to print the multi table : "))

print("The multiplication table of : ",number)
for count in range(1,11): 
    print(number,'*',count,' = ',number*count)
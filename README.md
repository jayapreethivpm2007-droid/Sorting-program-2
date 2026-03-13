Bubble Sort Program 
def bubble_sort(arr):
    n = len(arr)
    for i in range(n):
        for j in range(0, n-i-1):
            if arr[j] > arr[j+1]:
                arr[j], arr[j+1] = arr[j+1], arr[j]

arr = [64, 34, 25, 12, 22]

bubble_sort(arr)

print("Sorted array:")
for i in arr:
    print(i),

Output:
Sorted array:
12 22 25 34 64

Selection Sort Program:
def selection_sort(arr):
    n = len(arr)

    for i in range(n):
        min_index = i
        for j in range(i+1, n):
            if arr[j] < arr[min_index]:
                min_index = j

        arr[i], arr[min_index] = arr[min_index], arr[i]

arr = [29, 10, 14, 37, 13]

selection_sort(arr)

print("Sorted array:")
for i in arr:
    print(i),

Output:
Sorted array:
10 13 14 29 37

Insertion Sort Program:
def insertion_sort(arr):

    for i in range(1, len(arr)):
        key = arr[i]
        j = i-1

        while j >= 0 and key < arr[j]:
            arr[j+1] = arr[j]
            j -= 1

        arr[j+1] = key

arr = [12, 11, 13, 5, 6]

insertion_sort(arr)

print("Sorted array:")
for i in arr:
    print(i),

Output :
Sorted array:
5 6 11 12 13

Radix Sort Program:

def counting_sort(arr, exp):
    n = len(arr)
    output = [0]*n
    count = [0]*10

    for i in range(n):
        index = arr[i]/exp
        count[(index)%10] += 1

    for i in range(1,10):
        count[i] += count[i-1]

    i = n-1
    while i >= 0:
        index = arr[i]/exp
        output[count[(index)%10]-1] = arr[i]
        count[(index)%10] -= 1
        i -= 1

    for i in range(n):
        arr[i] = output[i]

def radix_sort(arr):
    max1 = max(arr)
    exp = 1

    while max1/exp > 0:
        counting_sort(arr, exp)
        exp *= 10

arr = [170, 45, 75, 90, 802]

radix_sort(arr)

print("Sorted array:")
for i in arr:
    print(i),

Output:
Sorted array:
45 75 90 170 802

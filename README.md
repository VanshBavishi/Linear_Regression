# Linear_Regression
Implimentation of Linear Regression witth one variable to predict profits for a restaurant franchise.


a = int(input("Total banana : "))
b = int(input("Distance : "))
c = int(input("Max load : "))

lost = 0
rem = a

for i in range(b):
    while rem > 0:
        rem -= c
        if rem == 1:
            lost -= 1
        lost += 2
    lost -= 1
    rem = a - lost
    if rem == 0:
        print("Not possible")
        break
print("Ans " + str(rem))




X = dict()
Y = dict()
A = {"a": 0.2, "b": 0.3, "c": 0.6, "d": 0.6}
B = {"a": 0.9, "b": 0.9, "c": 0.4, "d": 0.5}

print(A)
print(B)

for i, j in zip(A, B):
    a = A[i]
    b = B[j]
    if a > b:
        Y[i] = a
    else:
        Y[j] = b
print(Y)

for i in A:
    X[i] = 1 - A[i]

print(X)




graph = {
    'A': ['B', 'C'],
    'B': ['A', 'C', 'D'],
    'C': ['A', 'B', 'D', 'E'],
    'D': ['B', 'C', 'E'],
    'E': ['C', 'D']
}

colors = ['red', 'blue', 'green']

# Create a dictionary to store the color of each vertex
color_map = {}

# Assign the first available color to each vertex
for vertex in graph:
    used_colors = set(color_map.get(neighbour) for neighbour in graph[vertex])
    for color in colors:
        if color not in used_colors:
            color_map[vertex] = color
            break

# Print the color of each vertex
for vertex, color in color_map.items():
    print(f"{vertex}: {color}")




def solutions():
    # letters = ('s', 'e', 'n', 'd', 'm', 'o', 'r', 'y')
    all_solutions = list()
    for s in range(9, -1, -1):
        for e in range(9, -1, -1):
            for n in range(9, -1, -1):
                for d in range(9, -1, -1):
                    for m in range(9, 0, -1):
                        for o in range(9, -1, -1):
                            for r in range(9, -1, -1):
                                for y in range(9, -1, -1):
                                    if len(set([s, e, n, d, m, o, r, y])) == 8:
                                        send = 1000 * s + 100 * e + 10 * n + d
                                        more = 1000 * m + 100 * o + 10 * r + e
                                        money = 10000 * m + 1000 * o + 100 * n + 10 * e + y

                                        if send + more == money:
                                            all_solutions.append((send, more, money))
    return all_solutions

print(solutions())

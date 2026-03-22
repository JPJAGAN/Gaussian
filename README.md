# NAME: JAGAN J P
# REG.NO: 212224230099
# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
# Step 1: Input the number of unknowns n and read the augmented matrix of order n × (n+1).

# Step 2: Perform forward elimination to convert the matrix into upper triangular form (make all elements below the diagonal zero).

# Step 3: Apply back substitution to compute the values of unknown variables starting from the last equation.

# Step 4: Display the values of the variables X0,X1,X2,....

## Program:
```
# Program to find the solution of a matrix using Gaussian Elimination.
# Developed by: JAGAN J P
# RegisterNumber: 212224230099
n_and_values = list(map(float, input().split()))

n = int(n_and_values[0])
values = n_and_values[1:]

# Build augmented matrix
a = []
index = 0
for i in range(n):
    row = []
    for j in range(n + 1):
        row.append(values[index])
        index += 1
    a.append(row)

# Forward Elimination
for i in range(n):
    for j in range(i + 1, n):
        ratio = a[j][i] / a[i][i]
        for k in range(n + 1):
            a[j][k] -= ratio * a[i][k]

# Back Substitution
x = [0] * n
for i in range(n - 1, -1, -1):
    x[i] = a[i][n]
    for j in range(i + 1, n):
        x[i] -= a[i][j] * x[j]
    x[i] /= a[i][i]

# Output
for i in range(n):
    print(f"X{i} = {x[i]:.2f}", end=" ")
```

## Output:
<img width="630" height="823" alt="image" src="https://github.com/user-attachments/assets/00f34833-af14-44eb-8121-27aac20ae4fb" />

## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

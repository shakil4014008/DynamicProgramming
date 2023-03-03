# Basic
#  

```py

d = {1:0, 2:1}
def fib_topdown(n):
  if n < 2: 
    return n
  if n in d:
    return d[n]
  else: 
    d[n] = fib_topdown(n-1)+ fib_topdown(n-2)
    return d[n]

for i in range(0, 10):
  print(fib_topdown(i), end=' ')

print('\n')
# bottom up - tabular method
def fib_bottomup(n):
  table = [0, 1]
  for i in range(2, n + 1):
      table.append(fib_topdown(n-1)+ fib_topdown(n-2))
  return table[n]

for i in range(0, 10):
  print(fib_bottomup(i), end = ' ')

  

## Complexity Analysis
 T = O(n), S = O(n) 
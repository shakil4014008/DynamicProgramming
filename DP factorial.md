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

print('\n')
# T = (n), S = O(1)
def fibo(n):
  a, b = 0, 1
  for i in range(n):
    a, b = b, a + b
  return a 

print(fibo(100))

print('\n')

# factorial using top down memoization
d1 = {}
def fact(n):
  try:
    return d1[n]
  except KeyError: 
    if n == 0: 
      d1[n] = 1
      return d1[n]
    else: 
      d1[n] = n * fact(n-1)
      return d1[n]
print(fact(5))
      


# T = O(n), S = O(1) 
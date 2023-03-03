# dp
#  

```py
 
 def lcs_length(X, Y): # X, Y are list
  table = [[0 for j in range(len(Y)+1)] for i in range(len(X)+1)]
  for i, x in enumerate(X):
    for j, y in enumerate(Y):
      if x == y: 
        table[i+1][j+1] = table[i][j] + 1
      else: 
        table[i+1][j+1] = max(table[i+1][j], table[i][j+1])

  # read the substring out from the string
  result  = ""
  x, y  = len(X), len(Y)
  while x != 0 and y != 0: 
    if table[x][y] == table[x-1][y]: 
      x -= 1
    elif table[x][y] == table[x][y-1]:
      y -= 1
    else: 
      assert X[x-1] == Y[y-1]
      result = X[x-1]+result
      x -= 1
      y -= 1
  return result 


print(lcs_length('thisisatest','testingLCS123testing')+'\n')
print(lcs_length('this','thiss'))
      

## Complexity Analysis
 

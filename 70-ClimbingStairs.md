# Add Two Numbers
- You are climbing a stair case. It takes n steps to reach to the top.
- Each time you can either climb 1 or 2 steps. In how many distinct ways can you climb to the top?

### Note
* Number of distinc ways to climb N steps: Steps[N] = Steps[N-2] + Steps[N-1]
* Fibonacci sequence + dynamic programming(Need to take care of 3 initial cases)

## Dictionary Utilization
O(n)
```python
def climbStairs(self, n: int) -> int:
  if n <= 2:
      return n
  
  else:
      lastStep = n+1
      result = [0]*lastStep

      # Dynamic Programming for Fibonacci Sequence
      result[1] = 1
      result[2] = 2
      for index in range(3, lastStep):
          result[index] = result[index-2] + result[index-1]
      return result[n]
```
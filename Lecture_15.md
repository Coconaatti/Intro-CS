- Recursion can be used when you dont know how many times you're going to iterate through something, but yk the base case already!
- Fibonacci implementation is very important:
- ```py
  def fibonacci(n):
    if n == 0 or n == 1: # base case
        return 1
    else:
        return fibonacci(n-1) + fibonacci (n-2)
  ```
  - Notice how we didnt seperate the two functions from each other, i.e they're on the same line. If they weren't (i.e if each of them was returned but separately) , you were going to have a baad time :P. Because remember, a return statement  gives
 - Helper functions kinda act like encapsulation / abstraction stuff, the clients shouldn't be the ones dealing with it and they shouldn't know the implementation.
 - new expression: [short-circuit evaluation](https://en.wikipedia.org/wiki/Short-circuit_evaluation)
 - [stackoverflow answer](https://stackoverflow.com/questions/9344305/what-is-short-circuiting-and-how-is-it-used-when-programming-in-java)
 - divide-and-conquer is based on breaking down a problem to easier parts and solving each of it
 - " The key to making programs readable is locality. " -John V. Guttag
 - global variables are good for constants
 -  

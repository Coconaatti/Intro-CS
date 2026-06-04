- Lists are mutable, unlike tuples
- They are crazy!! I cant wait to tell you the full story.
- Empty lists are [], meanwhile singelton ones are written with the single value inside, unlike tuples which is sth like (2,)
- iterating through a list by values ( `` for e in L ``) is a bad idea, because if the list is mutated through the loop, you might get incorrect results, or maybe stay in an infinite loop.
- lists can be aliased. I think the same case is with strings, ranges, tuples, etc.
- However, assignment is bad bad! because assignment is the art of putting a label over a value, and re-assigning a variable with a label to a value doesn't delete the previous value, but just points the label to the new value.
- Think of it like having an arrow that points to something and changing "its pointing", or whatever.
- so lets say:
```
s = ["Hello"]
s1 = s
s = ["Hello world"]
```
s1 != s, but:
```
s = ["Hello"]
s1 = s
s.append("world")
```
s1 = s.  So reassignment doesn't mutate, but appending does.
- Object equality is not the same as value equality, because technically they differ in id.
- multiplying a list by 2 makes a duplicate *COPY* of the elements before it. A SHALLOW COPY! that means if you modify any of the elements, the other will be modified.
- for example:
```
L1 = [[]]*2
L2 = [[], []]
for i in range(len(L1)):
  L1[i].append(i)
  L2[i].append(i)
print('L1 =', L1, 'but', 'L2 =', L2)
# It prints L1 = [[0, 1], [0, 1]] but L2 = [[0], [1]]. 
```
- take this code also:
```
def append_val(val, list_1 = []):
  List_1.append(val) 
  print(list_1) # [3,4]

append_val(3) # I didn't set list_1 to be something , so list_1 will be used as if it was a normal variable
append_val(4)
# get it? :)
```

> _"When we append one list to another, e.g., Techs.append(Ivys),
> the original structure is maintained. The result is a list that contains
> a list. Suppose we do not want to maintain this structure, but want to
> add the elements of one list into another list. We can do that by using
> list concatenation (using the + operator) or the extend method."_
> The book

- Now comes the fun story!
- There was a finger exercise in the book that asked to print what happens when we append a list to itself. provided with the quote above, the whole list with the original structure is appended to itself, so basically what happens is that the list creates a reference of it self instead of creating a new object inside of it (Remember, append mutates and does not copy.) Copying however, whether you used a deep or shallow, works perfectly. reassigning doesn't work. but copying by ``L[:]`` works. when we append a list to itself, it marks that reference using ... , or ellipsis. I asked on stackoverflow what append does and what does that ellipsis represent but I got duplicated of course 🥀
- shallow copying references the content of an object (the memory block), while deep copying copies these objects themselves (or the whole object to be exact).

- Just one final notice:
```python
L1 = [2]
L2 = [L1, L1]
L3 = copy.deepcopy(L2)
L3[0].append(3)
print(L3)
```
this prints [[3,2],[3,2]] because L2 contains 2 exact object of L1, so they are both modified.

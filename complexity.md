- [Why do we tend to use log for representing logarithmic time complexity?](https://youtu.be/M4ubFru2O80?si=65JTbOlKvBVJdkQd)
- Why not just divide by two? well dividing by two is only one step of the total steps taken to finish your overall operation, meanwhile logarithms cover all of the steps requried.
- **big O vs big Θ**:
<img width="931" height="557" alt="image" src="https://github.com/user-attachments/assets/627829e8-fc91-4e83-99a2-41e9c29ba21b" />

[See also this answer](https://stackoverflow.com/a/471292). I liked the part specifically in: "so it will never be significantly faster or slower than stated." It's also called as tight bound to signify that it gets no more less than this or more than that. Functions like quick sort that have a worst case of O(n) and an average case of O(n log n) cannot be using a big theta
- **Merge sort**:
  Boy, it's a long story. First, you divide up your lists into two: right and left sides. Then you treat the right side as a parent list, and divide it into right and left. Same thing with the left side: treat it as a parent list, and divide it into right and left. Keep doing so until you end up having one single element in both sides. After that, you use another helper function to compare both elements, sort them, and check for any missing elements that haven't been sorted. It sorts them by creating an empty result list, compare the two elements, append the smaller one to the list, and check for any leftovers in both sides. If any left overs are found, we just put them straight into the result list (Since the rest is sorted itself, dont ask me why). It's almost close to what we were doing with selection sort. [Here's the python tutor link for a better visualization.](https://pythontutor.com/visualize.html#code=def%20merge%28right,%20left,%20compare%29%3A%0A%20%20%20%20result%20%3D%20%5B%5D%0A%20%20%20%20i,j%20%3D%200,%200%0A%20%20%20%20while%20i%20%3C%20len%28left%29%20and%20j%20%3C%20len%28right%29%3A%0A%20%20%20%20%20%20%20%20if%20compare%28left%5Bi%5D,%20right%5Bj%5D%29%3A%0A%20%20%20%20%20%20%20%20%20%20%20%20result.append%28left%5Bi%5D%29%0A%20%20%20%20%20%20%20%20%20%20%20%20i%20%2B%3D%201%0A%20%20%20%20%20%20%20%20else%3A%0A%20%20%20%20%20%20%20%20%20%20%20%20result.append%28right%5Bj%5D%29%0A%20%20%20%20%20%20%20%20%20%20%20%20j%20%2B%3D%201%0A%20%20%20%20while%20i%20%3C%20len%28left%29%3A%0A%20%20%20%20%20%20%20%20result.append%28left%5Bi%5D%29%0A%20%20%20%20%20%20%20%20i%20%2B%3D%201%0A%20%20%20%20while%20j%20%3C%20len%28right%29%3A%0A%20%20%20%20%20%20%20%20result.append%28right%5Bj%5D%29%0A%20%20%20%20%20%20%20%20j%20%2B%3D%201%0A%20%20%20%20return%20result%0A%0A%0Adef%20merge_sort%28L,%20compare%20%3D%20lambda%20x,%20y%3A%20x%20%3C%20y%29%3A%0A%20%20%20%20if%20len%28L%29%20%3C%202%3A%0A%20%20%20%20%20%20%20%20return%20L%5B%3A%5D%20%23%20actually,,%20why%20copy%3F%3F%20it%20works%20in%20both%20ways%0A%20%20%20%20else%3A%0A%20%20%20%20%20%20%20%20middle%20%3D%20len%28L%29%20//%202%0A%20%20%20%20%20%20%20%20left%20%3D%20merge_sort%28L%5B%3Amiddle%5D,%20compare%29%0A%20%20%20%20%20%20%20%20right%20%3D%20merge_sort%28L%5Bmiddle%3A%5D,%20compare%29%0A%20%20%20%20%20%20%20%20return%20merge%28left,%20right,%20compare%29%0A%0AL%20%3D%20%5B5,%2011,%2017,%2020,%2099,%20104,%206,%202%5D%0Aprint%28merge_sort%28L%29%29&mode=edit&origin=opt-frontend.js&py=311)
  Also an image from the lecture slides:
- **Selection sort**:
  The idea is basically starting at the very first index of the list, and checking if there's any smaller number than the one in the current index. So for index i, we iterate through ``L[i:]`` (<- prevents you from falling into an infinite loop) to see who's smaller than this index. IF there's an element that's smaller, they switch places, and the checking continues, but we check with the new element, is there anything smaller than this element? if no, we increase the index by one to continue searching. [Here's the implementation](https://pythontutor.com/visualize.html#code=def%20sel_sort%28L%29%3A%0A%20%20%20%20suffix_start%20%3D%200%0A%20%20%20%20while%20suffix_start%20!%3D%20len%28L%29%3A%0A%20%20%20%20%20%20%20%20for%20i%20in%20range%28suffix_start,%20len%28L%29%29%3A%0A%20%20%20%20%20%20%20%20%20%20%20%20print%28f%22suffix_start%3A%20%7Bsuffix_start%7D%22%29%0A%20%20%20%20%20%20%20%20%20%20%20%20print%28f%22i%3A%20%7Bi%7D%22%29%0A%20%20%20%20%20%20%20%20%20%20%20%20if%20L%5Bi%5D%20%3C%20L%5Bsuffix_start%5D%3A%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20L%5Bsuffix_start%5D,%20L%5Bi%5D%20%3D%20L%5Bi%5D,%20L%5Bsuffix_start%5D%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20print%28L%29%0A%20%20%20%20%20%20%20%20suffix_start%20%2B%3D%201%0A%20%20%20%20%0AL%20%3D%20%5B1,%205,%209,%202,%204,%200,%202%5D%0Asel_sort%28L%29&curInstr=3&mode=display&origin=opt-frontend.js&py=311) 
- **Some goofy terms**:
  - Asymptotic complexity: Why "asymptotic"? Answer: it means that something (our input) is approaching infinity, and we want to get the complexity of such an input. [Stackoverflow answer](https://cs.stackexchange.com/questions/53931/why-are-complexity-notations-called-asymptotic)
  - Amotizing your code: sure it means saving time by sorting, but how is amotizing related?
  -


> [!IMPORTANT]
> Check this little harmful function:
> ```python
> def loop(x):
>       y = 100
>       total = 0
>       for i in range(y):
>         total += x
>       return total
> ```
> You might think that the time complexity here is O(n), because look! the loop depends on the y right here. AND THAT'S WRONG! y here is not changable it is but that destroys the idea of functions, their purpose, and abstraction and decomposition. Because functions already provide input formal parameters that can be changed depending on your own input. Why modify the function itself? So that concludes: the determinant here is the x variable. Okay, but here the x variable is included in one arithmetic operation, nothing else, nothing harmful. So the complexity becomes O(1) No matter what x is. Usually when deciding a time complexity, check the input parameters and anything that can possibly affect your iterations, But these "things" better be mutable in first place. Ask yourself: can a client potentially change this variable?

Time complexity on data Types and their relative operations:
<img width="724" height="276" alt="image" src="https://github.com/user-attachments/assets/bea4cea0-65f1-429f-89dd-5b56c5b01005" />

Complexity Classes:
```
O(1) denotes *constant* running time.
O(log n) denotes *logarithmic* running time.
O(n) denotes *linear* running time.
O(n log n) denotes *log-linear* running time.
O(nk) denotes *polynomial* running time. Notice that k is a constant.
```

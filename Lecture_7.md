- functions can be treated as objects, this is called higher order programming, see https://en.wikipedia.org/wiki/Higher-order_programming
- Haskell is a programming language with the functional programming paradigm.
- formal parameters are these ambiguous arguments in the function signature.
- actual parameters are these which are passed in a function invokation.
- the function terminates on ``return``
- the point of execution is the cursor the compiler uses to point at the current step / instruction.
- Parameters allow programmers to write code that accesses not specific objects, but instead whatever objects the caller of the function chooses to use as actual parameters. This is called ``lambda abstraction``.

- *To inexperienced
programmers, writing test functions often seems to be a waste of
effort. Experienced programmers know, however, that an investment
in writing testing code often pays big dividends. It certainly beats
sitting at a keyboard and typing test cases into the shell over and
over during debugging (the process of finding out why a program
does not work, and then fixing it).*

- I used pytest today and I can approve that he got a point.
- keyword arguments are these arguments passed in the function invokation, in which the names of formal arguments are passed to actual values)
- Something like this: `` print(greeting(Key = "Hello", Value = "World")). ``
-  *In Python, you can always determine the scope of a name by looking at the program text. This is called static or lexical scoping.*
- global variables can be accessed in a function as an rvalue, not as an lvalue.
- functions work in LIFO "queueing" lol. (the last in is the first out)

- _**Decomposition** creates structure. It allows us to break a
program into parts that are reasonably self-contained and that may
be reused in different settings.
**Abstraction** hides detail. It allows us to use a piece of code as if
it were a black box—that is, something whose interior details we
cannot see, don't need to see, and shouldn't even want to see._

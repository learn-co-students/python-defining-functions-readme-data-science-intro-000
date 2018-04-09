
# Functions in Python

As we learn to accomplish more and more with our code, we want the ability to reuse our code to help us solve different problems.  Functions allow to do just that.  They also also give us the ability to name a sequence of operations, thus making our code expressive.  Let's see how this works and why something like this is useful.

### Our problem so far 

Imagine that we have chosen to visit one of our top travel destinations, Argentina. We just arrived at our hotel to meet our tour group, and a few of our fellow tourists are already there.


```python
fellow_tourists = ['jim', 'tracy', 'lisa']
```

> Press shift + enter to run this code.

We want to say hello to each of them with a friendly greeting. We could use a `for` loop to create a list of `friendly_greetings`.


```python
friendly_greetings = []
for fellow_tourist in fellow_tourists:
    friendly_greetings.append("Hi " + fellow_tourist + ", I'm so glad to be travelling with you!" )

friendly_greetings
```

Then a couple of hours later, a few more tourists arrive to join the group, and we want to greet them as well.


```python
fellow_tourists = ['steven', 'jan', 'meryl']
```

Well to accomplish, we would likely copy our code from above.


```python
friendly_greetings = []
for fellow_tourist in fellow_tourists:
    friendly_greetings.append("Hi " + fellow_tourist + ", I'm so glad to be travelling with you!" )
    
friendly_greetings
```

If each time we wanted to reuse code we needed to copy and paste the code, we would be having to maintain a lot more code than is necessary.  Also, each time we recopy our code presents another opportunity to make a mistake. What if there were a way to write that code just one time, yet be able to execute that code wherever and whenever we want? That's where functions come in.

Here is that same code wrapped in a function:


```python
def greet_fellow_tourists():
    friendly_greetings = []
    for fellow_tourist in fellow_tourists:
        friendly_greetings.append("Hi " + fellow_tourist + ", I'm so glad to be travelling with you!" )

    return friendly_greetings
```


```python
greet_fellow_tourists()
```

> Make sure to press shift + enter for the two cells above.

There are two steps to using a function: defining a function and executing a function.  Defining a function happens first, and afterwards when we call `greet_fellow_tourists()` we execute the function.   


```python
fellow_tourists = ['Jan', 'Joe', 'Avi']
greet_fellow_tourists()
```

Ok executing a function is fairly simple, just type the function's name followed by parentheses:


```python
greet_fellow_tourists()
```

Let's break down how to define or declare a function.

### Declaring and using functions

There are two components to declaring a function: the function signature and the function body.


```python
def name_of_function(): # signature
    words = 'function body' # body
```

#### Function Signature

The function signature is the first line of the function.  It follows the pattern of `def`, `function name`, `parentheses`, `colon`.

`def name_of_function():`

The `def` is there to tell Python that you are about to declare a function.  The name of the function indicates how to reference and execute the function later.  The colon is to end the function signature and indicate that the body of the function is next.  The parentheses are important as well, and we'll explain their use in a later lesson.

#### Function Body

The body of the function is what the function does.  This is the code that runs each time we execute the function.  We indicate that we are writing the function body by going to the next line after the colon and then indenting.  To complete the function body we stop indenting and make a new line.  


```python
def name_of_function(): 
    words = 'function body' # function body
# no longer part of the function body
```

Let's execute the `name_of_function` function.


```python
name_of_function()
```

> Press shift + enter

Did it work?  Kinda.  The lines of our function were run.  But our function did not return anything.  Functions are designed so that everything inside of them stay inside.  So for example, even though we declared the `words` variable, `words` is not available from outside of the function.


```python
words
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-40-993ed7d20d5f> in <module>()
    ----> 1 words
    

    NameError: name 'words' is not defined


To get something out of the function, we must use the `return` keyword, followed by what we would like to return.  Let's declare another function called `other_function` that has a body which is exactly the same, but has a return statement.


```python
def other_function(): # signature
    words = 'returned from inside the function body' # body
    return words
```


```python
other_function()
```




    'returned from inside the function body'



Much better.  So with the return statement we returned the string `'returned from inside the function body'`.

> We will devote an entire future lesson to what is available from inside and outside of the function.  So don't worry if it feels a little confusing right now.

### See it again

Now let's identify the function signature and function body of our original function, `greet_fellow_tourists()`.


```python
def greet_fellow_tourists(): # function signature
    friendly_greetings = [] # begin function body
    for fellow_tourist in fellow_tourists:
        friendly_greetings.append("Hi " + fellow_tourist + ", I'm so glad to be travelling with you!" )

    return friendly_greetings # return statement

# no longer in function body
```

As you can see, `greet_fellow_tourists()` has the same components of a function we identified earlier: the function signature, the function body, and the return statement. Each time we call, `greet_fellow_tourists()`, all of the lines in the body of the function are run.  However, only the return statement is accessible from outside of the function.


```python
greet_fellow_tourists()
```

### Summary

In this section we saw how using a function allows us to reuse code without rewriting it.  We saw that to declare a function we first write the function signature, which consists of the `def` keyword, the function name, parentheses and a colon.  We indicate the body of the function by indenting our code and then writing the code that our function will execute.  To execute the function, we write the function's name followed by parentheses.  Executing the function will run the lines in the body of the function.

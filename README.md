
# Introduction to functions

As we can accomplish more and more with code, we will want the ability to reuse these operations.  Functions will allow to do just that.  They also will also give us the ability to name a sequence of operations, thus making our code expressive.  Let's see how this works, and why something like this is useful.

### Our problem so far 

Imagine that we have a group of employees who have just joined our company.  


```python
new_employees = ['jim', 'tracy', 'lisa']
```

We want to send each of them a nice welcoming message.  We could use a `for` loop to create a list of `welcome_messages`.


```python
welcome_messages = []
for new_employee in new_employees:
    welcome_messages.append("Hi " + new_employee.title() + ", I'm so glad to be working with you!" )

welcome_messages
```




    ["Hi Jim, I'm so glad to be working with you!",
     "Hi Tracy, I'm so glad to be working with you!",
     "Hi Lisa, I'm so glad to be working with you!"]



Then a couple of weeks later, a few more employees join, and we want to send messages to them as well.


```python
new_employees = ['steven', 'jan', 'meryl']
```

Well to do, we would have to copy our code from above.


```python
welcome_messages = []
for new_employee in new_employees:
    welcome_messages.append("Hi " + new_employee.title() + ", I'm so glad to be working with you!" )
    
welcome_messages
```




    ["Hi Steven, I'm so glad to be working with you!",
     "Hi Jan, I'm so glad to be working with you!",
     "Hi Meryl, I'm so glad to be working with you!"]



If each time we wanted to reuse code we needed to copy and paste it, we would be having to maintain a lot more code than is necessary and each time we recopied it is another opportunity to make a mistake.  Now, what if there was a way to write that code just one time, yet be able to execute that code wherever and whenever we want?  Functions allow us to do just that.

Here is that same code wrapped in a function.


```python
def greet_employees():
    welcome_messages = []
    for new_employee in new_employees:
        welcome_messages.append("Hi " + new_employee.title() + ", I'm so glad to be working with you!" )

    return welcome_messages
```


```python
greet_employees()
```




    ["Hi Jan, I'm so glad to be working with you!",
     "Hi Joe, I'm so glad to be working with you!",
     "Hi Avi, I'm so glad to be working with you!"]



So note that there are two parts to a function.  Defining a function and executing a function.  The function is defined in the first block of code beginning with the keyword `def`.  However, declaring a function is like building a tool.  You do not put it to use until you use it.  To use, or execute the function, you write the name of the function followed by parentheses.  And note you can reuse the function as many times as you want.   


```python
new_employees = ['Jan', 'Joe', 'Avi']
greet_employees()
```




    ["Hi Jan, I'm so glad to be working with you!",
     "Hi Joe, I'm so glad to be working with you!",
     "Hi Avi, I'm so glad to be working with you!"]



Ok let's break down how to declare a function.

### Declaring and using functions

There are two components to declaring a function: the function signature and the function body.


```python
def name_of_function(): # signature
    words = 'function body' # body
```

#### Function Signature

The function signature is the first line of the function.  It follows the pattern of `def`, `function name`, `parentheses`, `colon`.

`def name_of_function():`

The `def` is there to tell Python that you are about to declare a function.  The name of the function is so we can reference the function later.  The colon is to end the function signature and indicate that next is the body of the function.  The parentheses are important as well, and we'll explain their use in a later lesson.

#### Function Body

The function body is what the function does.  This is the code that will be run each time we execute the function.  We indicate that we are writing the function body by indenting.  To end the function body we stop indenting.  Let's execute the `name_of_function` function.


```python
name_of_function()
```

Did it work?  Kinda.  The lines of our function were run.  But our function did not return anything.  Functions are designed so that everything inside of them stay inside.  So for example, even though we declared the `words` variable, that is not available from outside of the function.


```python
words
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-40-993ed7d20d5f> in <module>()
    ----> 1 words
    

    NameError: name 'words' is not defined


To get something out of the function, we must use the return keyword, followed by what we would like to return.  Let's declare another function called `other_function` that has a body which is exactly the same, but has a return statement.


```python
def other_function(): # signature
    words = 'function body' # body
    return words
```


```python
other_function()
other_function()
```




    'function body'



Much better.  So with the return statement we returned the string `'function body'`.

> We will devote an entire future lesson to what is available from inside and outside of the function.  So don't worry if it feels a little confusing right now.

### See it again

Now let's identify the function signature and function body of our original function, `greet_empoyees()`.


```python
def greet_employees(): # function signature
    welcome_messages = [] # begin function body
    for new_employee in new_employees:
        welcome_messages.append("Hi " + new_employee.title() + ", I'm so glad to be working with you!" )

    return welcome_messages # return statement
```

As you can see the same components of the function: the function signature, function body, and return statement were in that function as well. Each time we call, `greet_employees()`, all of the lines in the body of the function are run.  However, only the return statement is accessible from outside of the function.


```python
greet_employees()
```




    ["Hi Jan, I'm so glad to be working with you!",
     "Hi Joe, I'm so glad to be working with you!",
     "Hi Avi, I'm so glad to be working with you!"]



### Summary

In this section we saw how using a function allows us to reuse code without rewriting it.  We saw that to declare a function we first write the function signature, which consists of the `def` keyword, the function name, parentheses and a colon.  We indicate the body of the function by indenting our code and then writing the code that our function will execute.  To execute the function, we write the function's name followed by parentheses.  Executing the function will run the lines in the body of the function.

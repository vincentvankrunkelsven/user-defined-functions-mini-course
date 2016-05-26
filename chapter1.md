---
title       : User-defined Functions
description : Recall prior knowledge on how to use functions and learn to develop your own functions
attachments :
  slides_link : https://s3.amazonaws.com/assets.datacamp.com/course/teach/slides_example.pdf

--- type:VideoExercise lang:python xp:50 skills:1 key:9a600c4910
## Introduction to user-defined functions

Welcome to the course! My name is Francis and in this course, you'll learn to define your own functions. 

Specifically, you will be learning to do the following:

- define functions without parameters,
- define functions with single parameters, and
- define functions that return a single value.

Let's begin!

You've learned how to use built-in functions in Python such as `print()` and `str()`.

Recall that `print()` accepts a string (or a set of strings) and prints the string out into the shell. For example:

```
print('Hello DataCamp!')
```

The `str()` function accepts an object such as a number and returns a string object. You can assign a call to `str()` to a variable to store its return value.

```
a_number = str(5)
```

Unlike `str()`, the return value of `print()` is `NoneType`, which basically means that it doesn't have a return value.


**Writing your own function**

While built-in Python functions are cool, you will need functions that have functionality specific to your needs. Fortunately, you can define your own functions in Python!

To start a function definition, 

- begin with the keyword `def`, 
- followed by a _function name_, 
- a set of _parentheses_ `()`, which will later contain parameters you will define,
- and a _colon_ `:`. 
 
Let's define a function that squares a number. The function name `square` is perfect for this. Following the steps above, you will get the following:

```def square():```

The code above is called a **function header**, which shows the keyword `def`, followed by the name of the function, a set of _parentheses_, and a _colon_. To complete the function definition, complete the _function body_ by squaring a value, say 4, and printing the output:

```
def square():
    new_value = 4 ** 2
    print(new_value)
```
Right now, the `square()` function does not have any parameters within the `()`. You will add them later. Now, whenever this function is called, the code that appears after the function header is run. In this case, `new_value` is assigned the value of $4 ** 2$ and then printed out.

You can call the function as you do with pre-built functions: `square()`. This should yield the value, _16_.

This isn't as helpful, though. What if you wanted to square any other number besides 4? To do that, you add a **parameter** to the function in between the parentheses. A parameter allows the user of the function to _pass arguments_ to the function so it can process different values. 

A quick word on using _parameters_ vs. _arguments_:

- When you _define_ a function, you have **parameters** in the function header.
- When you _call_ a function, you _pass_ **arguments** into the function.

Let's now add a _parameter_ to our `square()` function. For example:

```
def square(value):
    new_value = value ** 2
    print(new_value)
```

Your function now has the `value` parameter, which accepts an _argument_ passed to `square` when called. In the function body, the variable `new_value` takes the square of _value_, which is then printed out.

You've now defined a function `square` that accepts a single parameter and prints out its squared value. But what if you don't want to print that value directly and instead just return the squared value and assign it to some variable? You can have your function return the new value by adding the `return` statement, followed by the value or variable to return.

```
def square(value):
    new_value = value ** 2
    return new_value
```

Now your `square` function returns the value instead of printing it. Let's call the `square()` function and pass the number 4 as an argument:

```
num = square(4)
```

In the example above, the value _4_ was passed to the function call to `square()`. Also note that the function call is assigned to the variable `num`. Because `square()` returns a value, the value it _returns_ will get stored in `num`, which you can later on use for other computations.

You've now just learned the basics of defining your own functions! Now it's your turn. In the next few exercises, you will try your hand at defining and using your own functions. 

*** =video_link
//player.vimeo.com/video/154783078


--- type:MultipleChoiceExercise lang:python xp:50 skills:1 key:0ecf40f893
## Recapping the use of functions

Let's do a recap of what you know about using built-in functions. Here, you will use the `str()` and `print()` functions and figure out which function returns a value. A variable `x` has been preloaded for this exercise.

In the IPython shell, do the following:

- Assign `str(x)` to a variable `y1`: `y1 = str(x)`
- Assign `print(x)` to a variable `y2`: `y2 = print(x)`
- Check the types of the variables `x`, `y1`, and `y2`.

What are the types of `x`, `y1`, and `y2`?

*** =instructions
- They are all `str` types.
- `x` is a `float`, `y1` is an `float`, and `y2` is a `str`.
- `x` is a `float`, `y1` is a `str`, and `y2` is a `NoneType`.
- They are all `NoneType` types.

*** =hint
- Recall the function `type()` and use it to check the types of the variables.

*** =pre_exercise_code
```{r}
# The pre exercise code runs code to initialize the user's workspace. You can use it for several things:
# Preload variables and values
x = 4.89
```

*** =sct
```{python}
test_mc(correct = 3, 
        msgs = ["No, not all are strings. Use the `type()` function to check!",
                "Not quite. What do `str()` and `print()` output again?",
                "Correct!",
                "No, not all are `NoneType`s. Use the type function to check!"])
```


--- type:NormalExercise lang:python xp:100 skills:1 key: key:22ba90bcbd
## Writing a simple function

In the last lecture, Francisco described the basics of how to define a function. You will now write your own function!

Define a function, `shout`, which simply prints out a string with three exclamation marks `'!!!'` at the end. 

You will **concatenate** the string with the exclamation marks. Recall that you can do this with the `+` operator.

*** =instructions
- Complete the function header by adding the appropriate function name, `shout`.
- In the function body, concatenate the string, `'congratulations'` with another string, `'!!!'`. Assign the result to `shout_word`.
- Print the value of `shout_word`.
- Call the `shout` function.

*** =hint
- The recipe for concatenating two strings is: _string1_ `+` _string2_.
- The recipe for calling functions without arguments is _function name_`()`.

*** =pre_exercise_code
```{python}
# The pre exercise code runs code to initialize the user's workspace. You can use it for several things:

# 1. Preload a dataset. The code below will read the csv that is stored at the URL's location.

# 2. Preload a package

```

*** =sample_code
```{python}
# Define the function shout
def ___():

    # Concatenate the string 'congratulations' to '!!!' and assign to shout_word
    

    # Print the value of shout_word
    print(___)

# Call the shout function

```

*** =solution
```{python}
# Define the function shout
def shout():

    # Concatenate the string 'congratulations' to '!!!' and assign to shout_word
    shout_word = 'congratulations' + '!!!'

    # Print the value of shout_word
    print(shout_word)

# Call the shout function
shout()
```

*** =sct
```{python}
# The sct section defines the Submission Correctness Tests (SCTs) used to
# evaluate the student's response. All functions used here are defined in the 
# pythonwhat Python package. Documentation can also be found at github.com/datacamp/pythonwhat/wiki

success_msg("Great work!")
```


--- type:NormalExercise lang:python xp:100 skills:1 key:3d1bbbef0d
## Writing a simple function that takes an argument

Congratulations! You have successfully defined _and_ called your own function! That's pretty cool.

In the previous exercise, you defined and called the function `shout()`, which printed out a string concatenated with `'!!!'`.

```
def shout():
    shout_word = 'congratulations' + '!!!'
    print(shout_word)
```

You will now update `shout()` by adding a _parameter_ so that it can accept and process any string _argument_ passed to it.

*** =instructions
- Complete the function header by adding the parameter name, `word`.
- Assign the result of concatenating `word` with `'!!!'` to `shout_word`.
- Print the value of `shout_word`.
- Call the `shout` function, passing to it the string, `congratulations`.

*** =hint
- Use the parameter `word` to form the new value to be assigned to `shout_word`.
- Pass the argument `'congratulations'` to the function `shout`.

*** =pre_exercise_code
```{python}
# The pre exercise code runs code to initialize the user's workspace. You can use it for several things:

# 1. Preload a dataset. The code below will read the csv that is stored at the URL's location.

# 2. Preload a package

```

*** =sample_code
```{python}
# Define the function shout, which accepts the parameter word
def shout(___):

    # Concatenate the string in word with '!!!' and assign to shout_word
    ___ = ___ + '!!!'

    # Print the value of shout_word
    print(___)

# Call the shout function, with the string 'congratulations'

```

*** =solution
```{python}
# Define the function shout, which accepts the parameter word
def shout(word):

    # Concatenate the string in word with '!!!' and assign to shout_word
    shout_word = word + '!!!'

    # Print the value of shout_word
    print(shout_word)

# Call the shout function, with the string 'congratulations'
shout('congratulations')
```

*** =sct
```{python}
# The sct section defines the Submission Correctness Tests (SCTs) used to
# evaluate the student's response. All functions used here are defined in the 
# pythonwhat Python package. Documentation can also be found at github.com/datacamp/pythonwhat/wiki

success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:1  key:cd2b04a649
## Writing simple functions that return a single value

You're getting very good at this! Try your hand at another modification to the `shout()` function so that it now _returns_ a single value.

Modify the `shout()` function you wrote earlier such that instead of printing within the `shout()` function, you _return_ a value instead. Parts of the function `shout()`, which you wrote earlier, are shown.

*** =instructions
- In the function body, concatenate the string in `word` with `'!!!'` and assign to `shout_word`.
- Replace the `print` statement with the appropriate `return` statement.
- Call the `shout` function, passing to it the string, `congratulations`, and assigning the call to the variable, `yell`.
- To check if `yell` contains the value returned by `shout()`, print the value of `yell`

*** =hint
- You concatenate strings with the use of the `+` operator.
- Make sure you assign the `shout()` function call to `yell`.
- Don't forget to pass in the correct value for the argument when calling `shout()`.

*** =pre_exercise_code
```{python}
# The pre exercise code runs code to initialize the user's workspace. You can use it for several things:

# 1. Preload a dataset. The code below will read the csv that is stored at the URL's location.
# The movies variable will be available in the user's console.
import pandas as pd
movies = pd.read_csv("http://s3.amazonaws.com/assets.datacamp.com/course/introduction_to_r/movies.csv")

# 2. Preload a package
import numpy as np
```

*** =sample_code
```{python}
# Define the function shout, which accepts the parameter word
def shout (word):

    # Concatenate the string in word with '!!!' and assign to shout_word
    

    # Replace the print statement with the appropriate return statement
    print(shout_word)

# Call shout with the string 'congratulations' and assign the result to yell


# Print the value of yell

```

*** =solution
```{python}
# Define the function shout, which accepts the parameter word
def shout (word):

    # Concatenate the string in word with '!!!' and assign to shout_word
    shout_word = word + '!!!'

    # Replace the print statement with the appropriate return statement
    return shout_word

# Call shout with the string 'congratulations' and assign the result to yell
yell = shout('congratulations')

# Print the value of yell
print(yell)
```

*** =sct
```{python}
# The sct section defines the Submission Correctness Tests (SCTs) used to
# evaluate the student's response. All functions used here are defined in the 
# pythonwhat Python package. Documentation can also be found at github.com/datacamp/pythonwhat/wiki

success_msg("Great work!")
```

--- type:VideoExercise lang:python xp:50 skills:1 key:1558296060:929b1ddd2a
## Multiple arguments and return values

Welcome back! You're doing pretty well at defining your own functions, good job!

At this point, you already know how to define your own functions and even return values from them. What you'll learn next is how to pass multiple arguments to functions, as well as return not just one, but multiple values from them.

Let's tweak the `square()` function we've been working on a little bit more. Suppose that instead of simply squaring a value, you'd like to _raise_ a value to the power of another value that's also passed to the function. You can do this by having your function accept two parameters instead of just one. You should also change your function name to reflect this new behavior. Let's use `raise` as an appropriate function name:

```
def raise(value1, value2):
    new_value = value1 ** value2
    return new_value
```

Notice that there are now _two_ parameters in the function header instead of one, `value1` and `value2`. In the line after that, the behavior of the overall function was also changed by raising `value1` to the power of `value2`.

You can call the function by passing in _two_ arguments. The order in which the arguments are passed correspond to the order of the parameters in the function header. This means that when the following call is made:

``` 
raise(2, 3)
```

`value1` would contain 2 and `value2` would contain 3. Looking at the function body, this means that the computation `value1 ** value2` translates to `2 ** 3`. The function should return the value, 8.

***Returning multiple values***

You've seen how you can pass multiple arguments to functions you've defined, as well as return single values from your functions. You can also make your function return multiple values instead of just one. You can do that by constructing objects known as _tuples_.

A _tuple_ is like a list, in that it can contain multiple values. There are some differences, however: 

- Unlike a list, a tuple is _immutable_, that is, you cannot modify the values in a tuple once it has been constructed.
- While lists are defined using brackets `[]`, tuples are constructed using a set of parentheses `()`. 

You can add elements inside the parentheses as you do with lists, and then separate them with commas, like so: `(2, 4, 6)`

You can assign a tuple to a variable like usual: 

```
even_nums = (2, 4, 6)
```

You can also _unpack_ a tuple into several variables in one line: `a, b, c = (2, 4, 6)`. Doing so means that you assign to the variables _a_, _b_, and _c_ the tuple values, in the order that they appear in the tuple. This means that after _unpacking_, you have the following variable assignments: `a = 2`, `b = 4`, and `c = 6`.

Additionally, you can also access individual tuple elements like you do with lists: 

```
even_nums[1]
```

Doing so accesses the second element of the tuple. Why is that? Recall that with lists, you can use _zero-indexing_ to access list elements. You can do the same thing with tuples! Pretty cool, right?

Let's now modify the behavior of your `raise()` function. Instead of returning just the value of `value1` raised to the power of `value2`, let's also return the value of `value2` raised to the power of `value1`. You thus need to make `raise()` return _two_ values instead of one. Tuples can be used to do so:

```
def raise(value1, value2):
    
    new_value1 = value1 ** value2
    new_value2 = value2 ** value1
    
    new_tup = (new_value1, new_value2)
    
    return new_tup
```

Looking at the modifications to `raise()`. Notice that in addition to the `value1 ** value2` computation, you also compute `value2 ** value1`. A tuple is then constructed, composed of the results in `new_value1` and `new_value2`, and assigned to `new_tup`. Lastly, the tuple is returned, which now contains our two new values.

*** =video_link
//player.vimeo.com/video/154783078


--- type:NormalExercise lang:python xp:100 skills:1  key:419a27dc8b
## Writing simple functions that accept multiple arguments

Francisco discussed the use of multiple parameters in defining functions in the last lecture. You are now going to use what you've learned to modify the `shout()` function further.

Here, you will modify `shout()` to accept two arguments. Parts of the function `shout()`, which you wrote earlier, is shown.

*** =instructions
- Modify the function header such that it accepts two parameters, `word1` and `word2`, in that order.
- Concatenate each of `word1` and `word2` with `'!!!'` and assign to `shout1` and `shout2`, respectively.
- Concatenate `shout1` and `shout2` together, in that order, and assign to `new_shout`.
- Pass the strings `'congratulations'` and `'you'`, in that order, to a call to `shout()`. Assign the return value to `yell`.

*** =hint
- Make sure that `word1` and `word2` are in the right order.
- Don't forget to concatenate `shout1` and `shout2`, in that order, for the return variable.
- Make sure that `yell` receives the output from the call to `shout()`.

*** =pre_exercise_code
```{python}
# The pre exercise code runs code to initialize the user's workspace. You can use it for several things:

# 1. Preload a dataset. The code below will read the csv that is stored at the URL's location.

# 2. Preload a package

```

*** =sample_code
```{python}
# Define the function shout, which accepts the parameters word1 and word2
def shout(___, ___):

    # Concatenate word1 with '!!!' and assign to shout1
    
    
    # Concatenate word2 with '!!!' and assign to shout2
    
    
    # Concatenate shout1 with shout2 and assign to new_shout
    

    # Return new_shout
    return new_shout

# Call shout with the strings 'congratulations' and 'you' and assign the result to yell


# Print the value of yell
print(yell)
```

*** =solution
```{python}
# Define the function shout, which accepts the parameters word1 and word2
def shout(word1, word2):

    # Concatenate word1 with '!!!' and assign to shout1
    shout1 = word1 + '!!!'
    
    # Concatenate word2 with '!!!' and assign to shout2
    shout2 = word2 + '!!!'
    
    # Concatenate shout1 with shout2 and assign to new_shout
    new_shout = shout1 + shout2

    # Return new_shout
    return new_shout

# Call shout with the strings 'congratulations' and 'you' and assign the result to yell
yell = shout('congratulations', 'you')

# Print the value of yell
print(yell)
```

*** =sct
```{python}
# The sct section defines the Submission Correctness Tests (SCTs) used to
# evaluate the student's response. All functions used here are defined in the 
# pythonwhat Python package. Documentation can also be found at github.com/datacamp/pythonwhat/wiki

success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:50 skills:1  key:ee3e217dd9
## A brief introduction to tuples

Alongside learning about functions, you've also learned about tuples! Here, you will practice what you've learned about tuples: how to construct, unpack, and access tuple elements.

A three-element tuple named `nums` has been preloaded for this exercise.

*** =instructions
- Print out the value of `nums` in the IPython shell. Note the elements in the tuple.
- In the IPython shell, try to change the first element of `nums` to the value _2_ by doing an assignment: `nums[0] = 2`. What happens?
- Unpack `nums` to the variables `num1`, `num2`, and `num3`.
- Construct a new tuple, `even_nums` composed of the same elements in `nums`, but with the odd-numbered elements replaced with the value, _2_.

*** =hint
- The number of elements in `nums` determines how many variables you'll need to unpack them to.
- You construct tuples with _parentheses_ `()`.

*** =pre_exercise_code
```{python}
# The pre exercise code runs code to initialize the user's workspace. You can use it for several things:

# 3. Preload variables and values
nums = (3,4,6)
```

*** =sample_code
```{python}
# Unpack the tuple nums into the variables num1, num2, and num3


# Construct the tuple even_nums

```

*** =solution
```{python}
# Unpack the tuple nums into the variables num1, num2, and num3
num1, num2, num3 = nums

# Construct the tuple even_nums
even_nums = (2, num2, num3)
```

*** =sct
```{python}
# The sct section defines the Submission Correctness Tests (SCTs) used to
# evaluate the student's response. All functions used here are defined in the 
# pythonwhat Python package. Documentation can also be found at github.com/datacamp/pythonwhat/wiki

# Check if the student changed the unpacked nums to num1, num2, and num3 correctly
test_object("num1", 
            incorrect_msg="Did you unpack `nums` to the correct variables?")
test_object("num2",
            incorrect_msg="Did you unpack `nums` to the correct variables?")
test_object("num3",
            incorrect_msg="Did you unpack `nums` to the correct variables?")

success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:1  key:9377e3271f
## Write a function that returns multiple values

In the previous exercise, you constructed tuples, assigned tuples to variables, and unpacked tuples. Here you will return mutiple values from a function using tuples.

Let's now update our `shout()` function to return multiple values. Instead of returning just one string, we will return two strings with the string `!!!` concatenated to each. 

*** =instructions
- Modify the function header such that the function name is now `shout_all`, and it accepts two parameters, `word1` and `word2`, in that order.
- Concatenate the string `'!!!'` to each of `word1` and `word2` and assign to `shout1` and `shout2`, respectively.
- Construct a tuple `shout_words`, composed of `shout1` and `shout2`.
- Call `shout_all` with the strings `'congratulations'` and `'you'` and assign the result to yell1 and yell2


*** =hint
- You concatenate strings with the use of the `+` operator.
- Check that you have the correct number of parameters in the function header.
- Remember that tuples are constructed with parentheses `()`.
- Make sure you unpack the result of `shout_all()` into the right number of variables.

*** =pre_exercise_code
```{python}
# The pre exercise code runs code to initialize the user's workspace. You can use it for several things:

# 1. Preload a dataset. The code below will read the csv that is stored at the URL's location.

# 2. Preload a package

```

*** =sample_code
```{python}
# Define the function shout_all, which accepts the parameters word1 and word2
def shout(___, ___):

    # Concatenate the string '!!!' to word1 and assign to shout1
    
    
    # Concatenate the string '!!!' to word2 and assign to shout2
    
    
    # Construct a tuple, shout_words, that contains shout1 and shout2
    

    # Return shout_words
    return shout_words

# Call shout_all with the strings 'congratulations' and 'you' and assign the result to yell1 and yell2


# Print the values of yell1 and yell2
print(yell1)
print(yell2)
```

*** =solution
```{python}
# Define the function shout_all, which accepts the parameters word1 and word2
def shout_all(word1, word2):

    # Concatenate the string '!!!' to word1 and assign to shout1
    shout1 = word1 + '!!!'
    
    # Concatenate the string '!!!' to word2 and assign to shout2
    shout2 = word2 + '!!!'
    
    # Construct a tuple, shout_words, that contains shout1 and shout2
    shout_words = (shout1, shout2)

    # Return shout_words
    return shout_words

# Call shout with the strings 'congratulations' and 'you' and assign the result to yell1 and yell2
yell1, yell2 = shout_all('congratulations', 'you')

# Print the values of yell1 and yell2
print(yell1)
print(yell2)
```

*** =sct
```{python}
# The sct section defines the Submission Correctness Tests (SCTs) used to
# evaluate the student's response. All functions used here are defined in the 
# pythonwhat Python package. Documentation can also be found at github.com/datacamp/pythonwhat/wiki

success_msg("Great work!")
```

---
title       : User-defined Functions
description : Recall prior knowledge on how to use functions and learn to develop your own functions
attachments :
  slides_link : https://s3.amazonaws.com/assets.datacamp.com/course/teach/slides_example.pdf

--- type:VideoExercise lang:python xp:50 skills:1 key:9a600c4910
## Introduction to user-defined functions

*** =video_link
//player.vimeo.com/video/154783078

--- type:MultipleChoiceExercise lang:python xp:50 skills:1 key:0ecf40f893
## Recapping the use of functions

You've learned to use built-in functions in Python such as `print()` and `int()`.

You know that `print()` accepts a string (or a set of strings) and prints the string out into the shell. For example:

```
print('Hello DataCamp!')
```

The `int()` function accepts an object such as a number or string and returns an integer object. You can assign a call to `int()` to a variable to store its return value.

```
a_number = int('5')
```

Unlike `int()`, the return value of `print()` is `NoneType`, which basically means that it doesn't have a return value.

For this exercise, a variable `x` has been preloaded. In the IPython shell, do the following:

- Assign `int(x)` to a variable `y1`: `y1 = int(x)`
- Assign `print(x)` to a variable `y2`: `y2 = print(x)`
- Recall the function `type()`. Use it to check out the types of `x`, `y1`, and `y2`.

What are the types of `x`, `y1`, and `y2`?

*** =instructions
- They are all `float` types.
- `x` is an `int`, `y1` is an `int`, and `y2` is a `float`.
- `x` is a `float`, `y1` is an `int`, and `y2` is a `NoneType`.
- They are all `None` types.

*** =hint
Recall the return values of the `print()` and `int()` functions.

*** =pre_exercise_code
```{r}
# The pre exercise code runs code to initialize the user's workspace. You can use it for several things:

# 1. Pre-load packages, so that users don't have to do this manually.
import pandas as pd
import matplotlib.pyplot as plt

# 2. Preload a dataset. The code below will read the csv that is stored at the URL's location.
# The movies variable will be available in the user's console.
movies = pd.read_csv("http://s3.amazonaws.com/assets.datacamp.com/course/introduction_to_r/movies.csv")

# 3. Create a plot in the viewer, that students can check out while reading the exercise
#plt.scatter(movies.runtime, movies.rating)
#plt.show()

# 4. Preload variables and values
x = 4.89
```

*** =sct
```{r}
# The sct section defines the Submission Correctness Tests (SCTs) used to
# evaluate the student's response. All functions used here are defined in the 
# pythonwhat Python package

msg_bad = "That is not correct!"
msg_success = "Exactly! The correlation is very weak though."

# Use test_mc() to grade multiple choice exercises. 
# Pass the correct option (Action, option 2 in the instructions) to correct.
# Pass the feedback messages, both positive and negative, to feedback_msgs in the appropriate order.
test_mc(4, [msg_bad, msg_bad, msg_bad, msg_success]) 
```

--- type:NormalExercise lang:python xp:100 skills:1 key:3d1bbbef0d
## Writing simple functions that take an argument

While built-in Python functions are cool, you will need functions that have functionality specific to your needs. Fortunately, you can define your own functions in Python!

To start a function definition, 

- begin with the keyword `def`, 
- followed by a _function name_, 
- a set of _parentheses_ `()`, 
- and a _colon_ `:`. 
 
Create a function that squares a number. The function name `square` is perfect for this. Following the steps above, you will get the following:

```def square():```

The code above is called a _function header_, which shows the keyword `def`, followed by the name of the function. You will add to this later. To complete the function definition, complete the _function body_ by squaring a value, say 4, and printing the output:

```
def square():
    new_value = 4 ** 2
    print(new_value)
```

You can call the function as you do with pre-built functions: `square()`. This should yield the value, _16_.

This isn't as helpful, though. What if you wanted to square any other number besides 4? To do that, you add a _parameter_ to the function in between the parentheses. A parameter allows the user of the function to _pass values_ to the function so it can process different values. Let's do that with the `square` function:

```
def square(value):
    new_value = value ** 2
    print(new_value)
```

Your function now has the `value` parameter, which accepts an argument passed to `square` when called. In the function body, the variable `new_value` takes the square of _value_, which is then printed out.

You will now define your own function. You will define the function `shout` which takes a string argument and prints out that string, appended with `'!!!'`.

*** =instructions
- Complete the function header by replacing the `_____` with the appropriate function name, `shout`.
- For the function parameter, replace the `_____` with the parameter name, `word`.
- In the function body, replace the appropriate `_____` with the `word` parameter. Assign the result to the variable `shout_word`.
- Print the value of `shout_word`.
- Call the `shout` function, passing to it the string, `help`.

*** =hint
- You don't have to program anything for the first instruction, just take a look at the first line of code.
- Use `import ___ as ___` to import `matplotlib.pyplot` as `plt`.
- Use `plt.scatter(___, ___, c = ___)` for the third instruction.
- You'll always have to type in `plt.show()` to show the plot you created.

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
def _____ (_____):

    # Concatenate the '!!!' string to word and assign to shout_word
    _____ = _____ + '!!!'

    # Print the value of shout_word
    print(_____)

# Call shout, with the string 'help'

```

*** =solution
```{python}
# Define the function shout, which accepts the parameter word
def shout (word):

    # Concatenate the '!!!' string to word and assign to shout_word
    shout_word = word + '!!!'

    # Print the value of shout_word
    print(shout_word)

# Call shout, with the string 'help'
shout('help')
```

*** =sct
```{python}
# The sct section defines the Submission Correctness Tests (SCTs) used to
# evaluate the student's response. All functions used here are defined in the 
# pythonwhat Python package. Documentation can also be found at github.com/datacamp/pythonwhat/wiki

# Check if the student changed the np.unique() call
# If it's not called, we know the student removed the call.
# If it's called incorrectly, we know the student changed the call.
test_function("numpy.unique",
              not_called_msg = "Don't remove the call of `np.unique` to define `ints`.",
              incorrect_msg = "Don't change the call of `np.unique` to define `ints`.")
# Check if the student removed the ints object
test_object("ints",
            undefined_msg = "Don't remove the definition of the predefined `ints` object.",
            incorrect_msg = "Don't change the definition of the predefined `ints` object.")

# Check if the student imported matplotlib.pyplot like the solution
# Let automatic feedback message generation handle the feedback messages
test_import("matplotlib.pyplot", same_as = True)

# Check whether the student used the scatter() function correctly
# If it's used, but incorrectly, tell them to check the instructions again
test_function("matplotlib.pyplot.scatter",
              incorrect_msg = "You didn't use `plt.scatter()` correctly, have another look at the instructions.")

# Check if the student called the show() function
# Let automatic feedback message generation handle all feedback messages
test_function("matplotlib.pyplot.show")

success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:1  key:cd2b04a649
## Writing simple functions that return a single value

You've defined a function `square` that accepts a single parameter and prints out its squared value. But what if you don't want to print the value directly and instead just return the squared value and assign it to some variable? You can have your function return the new value by adding the `return` statement, followed by the value or variable to return.

```
def square(value):
    new_value = value ** 2
    return new_value
```

Now that your `square` function returns the value instead of printing it, calling the function requires that you assign the result of the function to a variable so you can use the result later. Here's an example of how to do this:

```
num = square(4)
```

In the example above, the value _4_ was passed to `square()`. Because `square()` returns a value, the call is assigned to the variable `num`, which receives whatever value that the call to `square()` returns.

Modify the `shout()` function you wrote earlier to reflect a similar behavior. Instead of printing within the `shout()` function, return a value instead.

*** =instructions
- The function `shout()`, which you wrote earlier, is shown. Replace the `print` statement with the appropriate `return` statement.
- Concatenate the string `'!!!'` to word and assign to shout_word
- Call the `shout` function, passing to it the string, `help`, and assigning the call to the variable, `yell`.
- To check if `yell` contains the value returned by `shout()`, print the value of `yell`

*** =hint
- You don't have to program anything for the first instruction, just take a look at the first line of code.
- Use `import ___ as ___` to import `matplotlib.pyplot` as `plt`.
- Use `plt.scatter(___, ___, c = ___)` for the third instruction.
- You'll always have to type in `plt.show()` to show the plot you created.

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

    # Concatenate the string '!!!' to word and assign to shout_word
    

    # Replace the print statement with the appropriate return statement
    print(shout_word)

# Call shout with the string 'help' and assign the result to yell


# Print the value of yell

```

*** =solution
```{python}
# Define the function shout, which accepts the parameter word
def shout (word):

    # Concatenate the string '!!!' to word and assign to shout_word
    shout_word = word + '!!!'

    # Replace the print statement with the appropriate return statement
    return shout_word

# Call shout with the string 'help' and assign the result to yell
yell = shout('help')

# Print the value of yell
print(yell)
```

*** =sct
```{python}
# The sct section defines the Submission Correctness Tests (SCTs) used to
# evaluate the student's response. All functions used here are defined in the 
# pythonwhat Python package. Documentation can also be found at github.com/datacamp/pythonwhat/wiki

# Check if the student changed the np.unique() call
# If it's not called, we know the student removed the call.
# If it's called incorrectly, we know the student changed the call.
test_function("numpy.unique",
              not_called_msg = "Don't remove the call of `np.unique` to define `ints`.",
              incorrect_msg = "Don't change the call of `np.unique` to define `ints`.")
# Check if the student removed the ints object
test_object("ints",
            undefined_msg = "Don't remove the definition of the predefined `ints` object.",
            incorrect_msg = "Don't change the definition of the predefined `ints` object.")

# Check if the student imported matplotlib.pyplot like the solution
# Let automatic feedback message generation handle the feedback messages
test_import("matplotlib.pyplot", same_as = True)

# Check whether the student used the scatter() function correctly
# If it's used, but incorrectly, tell them to check the instructions again
test_function("matplotlib.pyplot.scatter",
              incorrect_msg = "You didn't use `plt.scatter()` correctly, have another look at the instructions.")

# Check if the student called the show() function
# Let automatic feedback message generation handle all feedback messages
test_function("matplotlib.pyplot.show")

success_msg("Great work!")
```

--- type:VideoExercise lang:python xp:50 skills:1 key:
## Multiple arguments and return values

*** =video_link
//player.vimeo.com/video/154783078


--- type:NormalExercise lang:python xp:100 skills:1  key:419a27dc8b
## Writing simple functions that accept multiple arguments

Let's tweak your `square` function a little bit more. Suppose that instead of simply squaring a value, you'd like to _raise_ a value to another value that's also passed to the function. You can do this by having your function accept two parameters instead of just one. You should also change your function name to reflect this new behavior. Let's use `raise` as an appropriate function name.

```
def raise(value1, value2):
    new_value = value1 ** value2
    return new_value
```

Notice that there are now _two_ parameters in the function header instead of one, `value1` and `value2`. In the line after that, the behavior of the overall function was also changed by raising `value1` to the power of `value2`.

The function is called by passing in _two_ arguments. The order in which the arguments are passed correspond to the order of the parameters in the function header. This means that when the following call is made:

``` raise(2, 3)```

`value1` would contain 2 and `value2` would contain 3. Looking at the function body, this means that the computation `value1 ** value2` translates to `2 ** 3`. The function should return the value, 8.

Modify the `shout()` function to accept two arguments.

*** =instructions
- The function `shout()`, which you wrote earlier, is shown. Modify the function header such that it accepts two parameters, `word1` and `word2`, in that order.
- Concatenate the string `'!!!'` to word1 and assign to `shout1`
- Concatenate the string `'!!!'` to word2 and assign to `shout2`
- Now, concatenate `shout1` and `shout2` together, in that order, and assign to `new_shout`
- Return the value of `new_shout`
- Pass the strings `'help'` and `'fire'`, in that order, to a call to `shout()`. Assign the return value to `yell`.
- Print the value of `yell`

*** =hint
- You don't have to program anything for the first instruction, just take a look at the first line of code.
- Use `import ___ as ___` to import `matplotlib.pyplot` as `plt`.
- Use `plt.scatter(___, ___, c = ___)` for the third instruction.
- You'll always have to type in `plt.show()` to show the plot you created.

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
# Define the function shout, which accepts the parameters word1 and word2
def _____ (_____, _____):

    # Concatenate the string '!!!' to word1 and assign to shout1
    
    
    # Concatenate the string '!!!' to word2 and assign to shout2
    
    
    # Concatenate word2 to word1 and assign to new_shout
    

    # Return new_shout
    

# Call shout with the strings 'help' and 'fire' and assign the result to yell


# Print the value of yell

```

*** =solution
```{python}
# Define the function shout, which accepts the parameters word1 and word2
def shout (word1, word2):

    # Concatenate the string '!!!' to word1 and assign to shout1
    shout1 = word1 + '!!!'
    
    # Concatenate the string '!!!' to word2 and assign to shout2
    shout2 = word2 + '!!!'
    
    # Concatenate word2 to word1 and assign to new_shout
    new_shout = word1 + word2

    # Return new_shout
    return new_shout

# Call shout with the strings 'help' and 'fire' and assign the result to yell
yell = shout('help', 'fire')

# Print the value of yell
print(yell)
```

*** =sct
```{python}
# The sct section defines the Submission Correctness Tests (SCTs) used to
# evaluate the student's response. All functions used here are defined in the 
# pythonwhat Python package. Documentation can also be found at github.com/datacamp/pythonwhat/wiki

# Check if the student changed the np.unique() call
# If it's not called, we know the student removed the call.
# If it's called incorrectly, we know the student changed the call.
test_function("numpy.unique",
              not_called_msg = "Don't remove the call of `np.unique` to define `ints`.",
              incorrect_msg = "Don't change the call of `np.unique` to define `ints`.")
# Check if the student removed the ints object
test_object("ints",
            undefined_msg = "Don't remove the definition of the predefined `ints` object.",
            incorrect_msg = "Don't change the definition of the predefined `ints` object.")

# Check if the student imported matplotlib.pyplot like the solution
# Let automatic feedback message generation handle the feedback messages
test_import("matplotlib.pyplot", same_as = True)

# Check whether the student used the scatter() function correctly
# If it's used, but incorrectly, tell them to check the instructions again
test_function("matplotlib.pyplot.scatter",
              incorrect_msg = "You didn't use `plt.scatter()` correctly, have another look at the instructions.")

# Check if the student called the show() function
# Let automatic feedback message generation handle all feedback messages
test_function("matplotlib.pyplot.show")

success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:50 skills:1  key:ee3e217dd9
## A brief introduction to tuples

You've seen how you can pass multiple arguments to functions you've defined, as well as have your function return a value. You can also make your function return multiple values instead of just one. You can do that by constructing _tuples_.

A _tuple_ is like a list, in that it can contain multiple values. Unlike a list, however, a tuple is _immutable_, that is to say you cannot modify the values in a tuple once it has been constructed.

Tuples are defined somewhat like lists. While lists use brackets `[]`, tuples are constructed using a set of parentheses `()`. You can add elements inside the parentheses as you do with lists, and then separate them with commas, like so:
`(2, 4, 6)`

You can assign a tuple to a variable like usual: 

```
even_nums = (2, 4, 6)
```

You can also _unpack_ a tuple into several variables in one line: `a, b, c = (2, 4, 6)`. Doing so means that you assign to the variables _a_, _b_, and _c_ the tuple values, in the order that they appear in the tuple. This means that after _unpacking_, the following assignments are made: `a = 2`, `b = 4`, and `c = 6`.

Additionally, you can also access individual tuple elements like you do with lists: 

```
even_nums[1]
```

A three-element tuple named `nums` has been preloaded for this exercise.

*** =instructions
- Print out the value of `nums` in the IPython shell. Note the elements in the tuple.
- In the IPython shell, try to change the first element of `nums` to the value _2_ by doing an assignment: `nums[0] = 2`. What happens?
- Construct a new tuple, `even_nums` composed of the same elements in `nums`, but with the odd-numbered elements replaced with the value, _2_. Use the variables `num1`, `num2`, and `num3` to unpack `nums`.

*** =hint
- You don't have to program anything for the first instruction, just take a look at the first line of code.
- Use `import ___ as ___` to import `matplotlib.pyplot` as `plt`.
- Use `plt.scatter(___, ___, c = ___)` for the third instruction.
- You'll always have to type in `plt.show()` to show the plot you created.

*** =pre_exercise_code
```{python}
# The pre exercise code runs code to initialize the user's workspace. You can use it for several things:

# 1. Preload a dataset. The code below will read the csv that is stored at the URL's location.
# The movies variable will be available in the user's console.
import pandas as pd
movies = pd.read_csv("http://s3.amazonaws.com/assets.datacamp.com/course/introduction_to_r/movies.csv")

# 2. Preload a package
import numpy as np

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

# Check if the student changed the np.unique() call
# If it's not called, we know the student removed the call.
# If it's called incorrectly, we know the student changed the call.
test_function("numpy.unique",
              not_called_msg = "Don't remove the call of `np.unique` to define `ints`.",
              incorrect_msg = "Don't change the call of `np.unique` to define `ints`.")
# Check if the student removed the ints object
test_object("ints",
            undefined_msg = "Don't remove the definition of the predefined `ints` object.",
            incorrect_msg = "Don't change the definition of the predefined `ints` object.")

# Check if the student imported matplotlib.pyplot like the solution
# Let automatic feedback message generation handle the feedback messages
test_import("matplotlib.pyplot", same_as = True)

# Check whether the student used the scatter() function correctly
# If it's used, but incorrectly, tell them to check the instructions again
test_function("matplotlib.pyplot.scatter",
              incorrect_msg = "You didn't use `plt.scatter()` correctly, have another look at the instructions.")

# Check if the student called the show() function
# Let automatic feedback message generation handle all feedback messages
test_function("matplotlib.pyplot.show")

success_msg("Great work!")
```

--- type:NormalExercise lang:python xp:100 skills:1  key:9377e3271f
## Write a function that returns multiple values

In the previous exercise, you've seen how to construct tuples, assign tuples to variables, and unpack tuples. Here you will learn how to return mutiple values from a function using tuples.

Let's modify the behavior of our `raise()` function. Instead of returning just the value of `value1` raised to the power of `value2`, also return the value of `value2` raised to the power of `value1`. You thus need to make your function return _two_ values instead of one. You will use tuples to do so:

```
def raise(value1, value2):
    
    new_value1 = value1 ** value2
    new_value2 = value2 ** value1
    
    new_tup = (new_value1, new_value2)
    
    return new_tup
```

Looking at the modifications to `raise()`. Notice that in addition to the `value1 ** value2` computation, you also compute `value2 ** value1`. A tuple is then constructed, composed of the results in `new_value1` and `new_value2`. Lastly, the tuple is returned, which now contains our two new values.

Let's now update our `shout()` function to return multiple values using tuples. Instead of returning just one string, we will return two strings with the string `!!!` concatenated to each. 

*** =instructions
- Modify the function header such that the function name is now `shout_all`, and it accepts two parameters, `word1` and `word2`, in that order.
- Concatenate the string `'!!!'` to each of `word1` and `word2` and assign to `shout1` and `shout2`, respectively.
- Construct a tuple `shout_words`, composed of `shout1` and `shout2`.
- Call `shout_all` with the strings `'help'` and `'fire'` and assign the result to yell1 and yell2


*** =hint
- You don't have to program anything for the first instruction, just take a look at the first line of code.
- Use `import ___ as ___` to import `matplotlib.pyplot` as `plt`.
- Use `plt.scatter(___, ___, c = ___)` for the third instruction.
- You'll always have to type in `plt.show()` to show the plot you created.

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
# Define the function shout_all, which accepts the parameters word1 and word2
def shout(_____, _____):

    # Concatenate the string '!!!' to word1 and assign to shout1
    
    
    # Concatenate the string '!!!' to word2 and assign to shout2
    
    
    # Construct a tuple, shout_words, that contains shout1 and shout2
    

    # Return shout_words
    return shout_words

# Call shout_all with the strings 'help' and 'fire' and assign the result to yell1 and yell2


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

# Call shout with the strings 'help' and 'fire' and assign the result to yell1 and yell2
yell1, yell2 = shout_all('help', 'fire')

# Print the values of yell1 and yell2
print(yell1)
print(yell2)
```

*** =sct
```{python}
# The sct section defines the Submission Correctness Tests (SCTs) used to
# evaluate the student's response. All functions used here are defined in the 
# pythonwhat Python package. Documentation can also be found at github.com/datacamp/pythonwhat/wiki

# Check if the student changed the np.unique() call
# If it's not called, we know the student removed the call.
# If it's called incorrectly, we know the student changed the call.
test_function("numpy.unique",
              not_called_msg = "Don't remove the call of `np.unique` to define `ints`.",
              incorrect_msg = "Don't change the call of `np.unique` to define `ints`.")
# Check if the student removed the ints object
test_object("ints",
            undefined_msg = "Don't remove the definition of the predefined `ints` object.",
            incorrect_msg = "Don't change the definition of the predefined `ints` object.")

# Check if the student imported matplotlib.pyplot like the solution
# Let automatic feedback message generation handle the feedback messages
test_import("matplotlib.pyplot", same_as = True)

# Check whether the student used the scatter() function correctly
# If it's used, but incorrectly, tell them to check the instructions again
test_function("matplotlib.pyplot.scatter",
              incorrect_msg = "You didn't use `plt.scatter()` correctly, have another look at the instructions.")

# Check if the student called the show() function
# Let automatic feedback message generation handle all feedback messages
test_function("matplotlib.pyplot.show")

success_msg("Great work!")
```

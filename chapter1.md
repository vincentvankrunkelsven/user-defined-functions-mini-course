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

You've learned to use built-in functions in Python such as `print()` and `type()`.

We know that `print()` accepts a string (or a set of strings) and prints the string out into the console. The `type()` function accepts an object and returns the type of that object.

*** =instructions
- Long movies, clearly
- Short movies, clearly
- Long movies, but the correlation seems weak
- Short movies, but the correlation seems weak

*** =hint
Have a look at the plot. Do you see a trend in the dots?

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
 
Let's create a function that squares a number. The function name `square` is perfect for this. Following the steps above, we get the following:

```def square():```

The code above is called a _function header_, which shows the keyword `def`, followed by the name of the function. You will add to this later. To complete the function definition, let's complete the _function body_ by squaring a value, say 4, and printing the output:

```
def square():
    new_value = 4 ** 2
    print( new_value )
```

You can call the function as you do with pre-built functions: `square()`. This should yield the value, _16_.

This isn't as helpful, though. What if we wanted to square any other number besides 4? To do that, we add a _parameter_ to the function in between the parentheses. A parameter allows the user of the function to _pass values_ to the function so it can process different values. Let's do that with our `square` function:

```
def square( value ):
    new_value = value ** 2
    print( new_value )
```

Our function now has the `value` parameter, which accepts an argument passed to `square` when called. In the function body, the variable `new_value` takes the square of _value_, which is then printed out.

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
def _____ ( _____ ):

    # Concatenate the '!!!' string to word and assign to shout_word
    _____ = _____ + '!!!'

    # Print the value of shout_word
    print( _____ )

# Call shout, with the string 'help'

```

*** =solution
```{python}
# Define the function shout, which accepts the parameter word
def shout ( word ):

    # Concatenate the '!!!' string to word and assign to shout_word
    shout_word = word + '!!!'

    # Print the value of shout_word
    print( shout_word )

# Call shout, with the string 'help'
shout( 'help' )
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

We've defined a function `square` that accepts a single parameter and prints out its squared value. But what if we don't want to print the value directly and instead just return the squared value and assign it to some variable? We can have our function return the new value by adding the `return` statement, followed by the value or variable to return.

```
def square( value ):
    new_value = value ** 2
    return new_value
```

Now that our `square` function returns the value instead of printing it, calling the function requires that you assign the result of the function to a variable so you can use the result later. Here's an example of how to do this:

```
num = square(4)
```

In the example above, the value _4_ was passed to `square()`. Because `square()` returns a value, the call is assigned to the variable `num`, which receives whatever value that the call to `square()` returns.

Let's modify the `shout()` function you wrote earlier to reflect a similar behavior. Instead of printing within the `shout()` function, return a value instead.

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
def shout ( word ):

    # Concatenate the string '!!!' to word and assign to shout_word
    

    # Replace the print statement with the appropriate return statement
    print( shout_word )

# Call shout with the string 'help' and assign the result to yell


# Print the value of yell

```

*** =solution
```{python}
# Define the function shout, which accepts the parameter word
def shout ( word ):

    # Concatenate the string '!!!' to word and assign to shout_word
    shout_word = word + '!!!'

    # Replace the print statement with the appropriate return statement
    return shout_word

# Call shout with the string 'help' and assign the result to yell
yell = shout( 'help' )

# Print the value of yell
print( yell )
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

--- type:NormalExercise lang:python xp:100 skills:1  key:419a27dc8b
## Writing simple functions that accept multiple arguments

Let's tweak our `square` function a little bit more. Suppose that instead of simply squaring a value, we'd like to _raise_ a value to another value that's also passed to the function. We can do this by having our function accept two parameters instead of just one. We should also change our function name to reflect this new behavior. Let's use `raise` as an appropriate function name.

```
def raise( value1, value2 ):
    new_value = value1 ** value2
    return new_value
```

Notice that there are now _two_ parameters in the function header instead of one, `value1` and `value2`. In the line after that, we also changed the behavior of the overall function by raising `value1` to the power of `value2`.

The function is called by passing in _two_ arguments. The order in which the arguments are passed correspond to the order of the parameters in the function header. This means that when the following call is made:

``` raise( 2, 3 )```

`value1` would contain 2 and `value2` would contain 3. Looking at the function body, this means that the computation `value1 ** value2` translates to `2 ** 3`. The function should return the value, 8.

Let's modify the `shout()` function to accept two arguments.

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
def _____ ( _____, _____ ):

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
def shout ( word1, word2 ):

    # Concatenate the string '!!!' to word1 and assign to shout1
    shout1 = word1 + '!!!'
    
    # Concatenate the string '!!!' to word2 and assign to shout2
    shout2 = word2 + '!!!'
    
    # Concatenate word2 to word1 and assign to new_shout
    new_shout = word1 + word2

    # Return new_shout
    return new_shout

# Call shout with the strings 'help' and 'fire' and assign the result to yell
yell = shout( 'help', 'fire' )

# Print the value of yell
print( yell )
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

--- type:NormalExercise lang:python xp:100 skills:1  key:ee3e217dd9
## A brief introduction to tuples

We've seen how we can pass multiple arguments to functions we've defined, as well as have our function return a value. We can also make our function return multiple values instead of just one. We do that by constructing _tuples_.

A tuple is like a list, in that it can contain multiple values. Unlike a list, however, a tuple is _immutable_, that is to say you cannot modify the values in a tuple once it has been constructed.

Tuples are defined somewhat like lists. While lists use brackets `[]`, tuples are constructed using a set of parentheses `()`. You can add elements inside the parentheses as you do with lists, and then separate them with commas, like so:
`(2, 4, 6)`

You can assign a tuple to a variable like usual: 

```
even_nums = (2, 4, 6)
```. 

You can also _unpack_ a tuple into several variables in one line: `a, b, c = (2, 4, 6)`. Doing so means that you assign to the variables _a_, _b_, and _c_ the tuple values, in the order that they appear in the tuple. This means that after _unpacking_, the following assignments are made: `a = 2`, `b = 4`, and `c = 6`.

If you assigned the tuple `(2, 4, 6)` to the variable `even_nums`, you can unpack `even_nums` into several variables too: `a, b, c = even_nums`.

*** =instructions
- The first function, `np.unique()`, uses the `unique()` function of the `numpy` package to get integer values for the movie genres. You don't have to change this code, just have a look!
- Import `pyplot` in the `matplotlib` package. Set an alias for this import: `plt`.
- Use `plt.scatter()` to plot `movies.runtime` onto the x-axis, `movies.rating` onto the y-axis and use `ints` for the color of the dots. You should use the first and second positional argument, and the `c` keyword.
- Show the plot using `plt.show()`.

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
# Get integer values for genres
_, ints = np.unique(movies.genre, return_inverse = True)

# Import matplotlib.pyplot


# Make a scatter plot: runtime on  x-axis, rating on y-axis and set c to ints


# Show the plot

```

*** =solution
```{python}
# Get integer values for genres
_, ints = np.unique(movies.genre, return_inverse = True)

# Import matplotlib.pyplot
import matplotlib.pyplot as plt

# Make a scatter plot: runtime on  x-axis, rating on y-axis and set c to ints
plt.scatter(movies.runtime, movies.rating, c=ints)

# Show the plot
plt.show()
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

In the previous exercise, we've seen how you can use tuples to make your functions return multiple values.

Here you'll modify the ___ function so that it returns more than one value when called.

*** =instructions
- The first function, `np.unique()`, uses the `unique()` function of the `numpy` package to get integer values for the movie genres. You don't have to change this code, just have a look!
- Import `pyplot` in the `matplotlib` package. Set an alias for this import: `plt`.
- Use `plt.scatter()` to plot `movies.runtime` onto the x-axis, `movies.rating` onto the y-axis and use `ints` for the color of the dots. You should use the first and second positional argument, and the `c` keyword.
- Show the plot using `plt.show()`.

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
# Get integer values for genres
_, ints = np.unique(movies.genre, return_inverse = True)

# Import matplotlib.pyplot


# Make a scatter plot: runtime on  x-axis, rating on y-axis and set c to ints


# Show the plot

```

*** =solution
```{python}
# Get integer values for genres
_, ints = np.unique(movies.genre, return_inverse = True)

# Import matplotlib.pyplot
import matplotlib.pyplot as plt

# Make a scatter plot: runtime on  x-axis, rating on y-axis and set c to ints
plt.scatter(movies.runtime, movies.rating, c=ints)

# Show the plot
plt.show()
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

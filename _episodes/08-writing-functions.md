---
title: "Writing Functions"
teaching: 15
exercises: 60
questions:
- "How can I create my own functions?"
objectives:
- "Explain and identify the difference between function definition and function call."
- "Write a function that takes a small, fixed number of arguments and produces a single result."
keypoints:
- "Break programs down into functions to make them easier to understand."
- "Define a function using `def` with a name, parameters, and a block of code."
- "Defining a function does not run it."
- "Arguments in call are matched to parameters in definition."
- "Functions may return a result to their caller using `return`."
---
## Break programs down into functions to make them easier to understand.

*   Human beings can only keep a few items in working memory at a time.
*   Understand larger/more complicated ideas by understanding and combining pieces.
    *   Components in a machine.
    *   Lemmas when proving theorems.
*   Functions serve the same purpose in programs.
    *   *Encapsulate* complexity so that we can treat it as a single "thing".
*   Also enables *re-use*.
    *   Write one time, use many times.

## Define a function using `def` with a name, parameters, and a block of code.

*   Begin the definition of a new function with `def`.
*   Followed by the name of the function.
    *   Must obey the same rules as variable names.
*   Then *parameters* in parentheses.
    *   Empty parentheses if the function doesn't take any inputs.
    *   We will discuss this in detail in a moment.
*   Then a colon.
*   Then an indented block of code.

~~~
def print_greeting():
    print('Hello!')
~~~
{: .python}

## Defining a function does not run it.

*   Defining a function does not run it.
    *   Like assigning a value to a variable.
*   Must call the function to execute the code it contains.

~~~
print_greeting()
~~~
{: .python}
~~~
Hello!
~~~
{: .output}

## Arguments in call are matched to parameters in definition.

*   Functions are most useful when they can operate on different data.
*   Specify *parameters* when defining a function.
    *   These become variables when the function is executed.
    *   Are assigned the arguments in the call (i.e., the values passed to the function).
    *   If you don't name the arguments when using them in the call, the arguments will be matched to
parameters in the order the parameters are defined in the function.

~~~
def print_date(year, month, day):
    joined = str(year) + '/' + str(month) + '/' + str(day)
    print(joined)

print_date(1871, 3, 19)
~~~
{: .python}
~~~
1871/3/19
~~~
{: .output}

Or, we can name the arguments when we call the function, which allows us to
specify them in any order:
~~~
print_date(month=3, day=19, year=1871)
~~~
{: .python}
~~~
1871/3/19
~~~
{: .output}

*   Via [Twitter](https://twitter.com/minisciencegirl/status/693486088963272705):
    `()` contains the ingredients for the function
    while the body contains the recipe.

## Functions may return a result to their caller using `return`.

*   Use `return ...` to give a value back to the caller.
*   May occur anywhere in the function.
*   But functions are easier to understand if `return` occurs:
    *   At the start to handle special cases.
    *   At the very end, with a final result.

~~~
def average(values):
    if len(values) == 0:
        return None
    return sum(values) / len(values)
~~~
{: .python}

~~~
a = average([1, 3, 4])
print('average of actual values:', a)
~~~
{: .python}
~~~
2.6666666666666665
~~~
{: .output}

~~~
print('average of empty list:', average([]))
~~~
{: .python}
~~~
None
~~~
{: .output}

*   Remember: [every function returns something]({{ page.root }}/04-built-in/).
*   A function that doesn't explicitly `return` a value automatically returns `None`.

~~~
result = print_date(1871, 3, 19)
print('result of call is:', result)
~~~
{: .python}
~~~
1871/3/19
result of call is: None
~~~
{: .output}

> ## Identifying Syntax Errors
>
> 1. Read the code below and try to identify what the errors are
>    *without* running it.
> 2. Run the code and read the error message.
>    Is it a `SyntaxError` or an `IndentationError`?
> 3. Fix the error.
> 4. Repeat steps 2 and 3 until you have fixed all the errors.
>
> ~~~
> def another_function
>   print("Syntax errors are annoying.")
>    print("But at least python tells us about them!")
>   print("So they are usually not too hard to fix.")
> ~~~
> {: .python}
>
> > ## Solution
> >
> > ~~~
> > def another_function():
> >   print("Syntax errors are annoying.")
> >   print("But at least Python tells us about them!")
> >   print("So they are usually not too hard to fix.")
> > ~~~
> > {: .python}
> {: .solution}
{: .challenge}

> ## Definition and Use
>
> What does the following program print?
>
> ~~~
> def report(pressure):
>     print('pressure is', pressure)
>
> print('calling', report, 22.5)
> ~~~
> {: .python}
> > ## Solution
> >
> > ~~~
> > calling <function report at 0x7fd128ff1bf8> 22.5
> > ~~~ 
> > {: .output}
> >
> > A function call always needs parenthesis, otherwise you get memory address of the function object. So, if we wanted to call the function named report, and give it the value 22.5 to report on, we could have our function call as follows
> > ~~~
> > print("calling")
> > report(22.5)
> > ~~~
> {: .solution}
{: .challenge}


> ## Order of Operations
>
> The example above:
>
> ~~~
> result = print_date(1871, 3, 19)
> print('result of call is:', result)
> ~~~
> {: .python}
>
> printed:
> ~~~
> 1871/3/19
> result of call is: None
> ~~~
> {: .output}
>
> Explain why the two lines of output appeared in the order they did.
>
> What's wrong in this example?
> ~~~
> result = print_date(1871,3,19)
>
> def print_date(year, month, day):
>    joined = str(year) + '/' + str(month) + '/' + str(day)
>    print(joined)
> ~~~
> {: .python}
> 
> > ## Solution
> > 
> > 1. The first line of output (`1871/3/19`) is from the print function inside `print_date()`, while the second line
> > is from the print function below the function call. All of the code inside `print_date()` is executed first, and
> > the program then "leaves" the function and executes the rest of the code.   
> > 2. The problem with the example is that the function is defined *after* the call to the function is made. Python
> > therefore doesn't understand the function call.
> {: .solution}
{: .challenge}

> ## Find the First
>
> Fill in the blanks to create a function that takes a list of numbers as an argument
> and returns the first negative value in the list.
> What does your function do if the list is empty?
>
> ~~~
> def first_negative(values):
>     for v in ____:
>         if ____:
>             return ____
> ~~~
> {: .python}
> > ## Solution
> >
> > ~~~
> > def first_negative(values):
> >     for v in values:
> >         if v<0:
> >             return v
> > ~~~
> > {: .python}
> > If an empty list is passed to this function, it returns `None`:
> > ~~~
> > my_list = []
> > print(first_negative(my_list)
> > ~~~
> > {: .python}
> > ~~~
> > None
> > ~~~
> > {: .output}
> {: .solution}
{: .challenge}

> ## Calling by Name
>
> Earlier we saw this function:
>
> ~~~
> def print_date(year, month, day):
>     joined = str(year) + '/' + str(month) + '/' + str(day)
>     print(joined)
> ~~~
> We saw that we can call the function using *named arguments*, like this:
> ~~~
> print_date(day=1, month=2, year=2003)
> ~~~
> {: .python}
>
> 1.  What does `print_date(day=1, month=2, year=2003)` print?
> 2.  When and why is it useful to call functions this way?
>
> > ## Solution
> > 
> > 1. `2003/2/1`
> > 2. Using named arguments can make code more readable since one can see from the function call what name the different arguments 
> > have inside the function. It can also reduce the chances of passing arguments in the wrong order, since by using named arguments 
> > the order doesn't matter.
> {: .solution}
{: .challenge}

> ## Encapsulate of If/Print Block
>
> The code below will run on a label-printer for chicken eggs.  A digital scale will report a chicken egg mass (in grams) to the computer and then the computer will print a label.  
>
> Please re-write the code so that the if-block is folded into a function.
>
> ~~~
>  import random
>  for i in range(10):
>
>     # simulating the mass of a chicken egg
>     # the (random) mass will be 70 +/- 20 grams
>     mass=70+20.0*(2.0*random.random()-1.0)
>
>     print(mass)
>    
>     #egg sizing machinery prints a label
>     if(mass>=85):
>        print("jumbo")
>     elif(mass>=70):
>        print("large")
>     elif(mass<70 and mass>=55):
>        print("medium")
>     else:
>        print("small")
> ~~~
> {: .python}
>
>
> The simplified program  follows.  What function definition will make it functional?
>
> ~~~
>  # revised version
>  import random
>  for i in range(10):
>
>     # simulating the mass of a chicken egg
>     # the (random) mass will be 70 +/- 20 grams
>     mass=70+20.0*(2.0*random.random()-1.0)
>
>     print(mass,print_egg_label(mass))    
>
> ~~~
> {: .python}
>
>
> 1. Create a function definition for `print_egg_label()` that will work with the revised program above.  Note, the function's return value will be significant. Sample output might be `71.23 large`.
> 2.  A dirty egg might have a mass of more than 90 grams, and a spoiled or broken egg will probably have a mass that's less than 50 grams.  Modify your `print_egg_label()` function to account for these error conditions. Sample output could be `25 too light, probably spoiled`.
>
> > ## Solution
> >
> > ~~~
> > def print_egg_label(mass):
> >     #egg sizing machinery prints a label
> >     if(mass>=90):
> >         return("warning: egg might be dirty")
> >     elif(mass>=85):
> >         return("jumbo")
> >     elif(mass>=70):
> >         return("large")
> >     elif(mass<70 and mass>=55):
> >         return("medium")
> >     elif(mass<50):
> >         return("too light, probably spoiled")
> >     else:
> >         return("small")
> > ~~~
> > {: .python}
> {: .solution}
{: .challenge}

> ## Simulating a dynamical system
>
> In mathematics, a [dynamical system](https://en.wikipedia.org/wiki/Dynamical_system) is a system in which a function describes the time dependence of a point in a geometrical space.  A canonical example of a dynamical system is a system called the [logistic map](https://en.wikipedia.org/wiki/Logistic_map).
>
>
> 1. Define a function called `logistic_map` that takes two inputs: `x`, representing the state of the system at time _t_, and a parameter `r`. This function should return a value representing the state of the system at time _t+1_.
>
> 2. Using a `for` loop, iterate the `logistic_map` function defined in part 1 starting from an initial condition of 0.5 for `t_final=10`, `100`, and `1000` periods. Store the intermediate results in a list so that after the `for` loop terminates you have accumulated a sequence of values representing the state of the logistic map at time _t=0,1,...,t_final_.
>
> 3. Encapsulate the logic of your `for` loop into a function called `iterate` that takes the initial condition as its first input, the parameter `t_final` as its second input and the parameter `r` as its third input. The function should return the list of values representing the state of the logistic map at time _t=0,1,...,t_final_.
>
>
{: .challenge}

> ## Error propagation
>
> In experimental work it is common for a quantity of interest to be calculated from a combination of direct measurements. It is important to remember that all 
>  experimentally measured quantities present an uncertainty that will affect the final result.
> 
> The uncertainty is determined by the measurement instrument and settings. For example, if we measure a triangle with a caliper (resolution 0.1mm) we will get a 
> more accurate value than if we use a ruler (resolution 1mm). But remember that whichever instrument we use we will introduce some amount of uncertainty.
> 
> This uncertainty can be quantified using error propagation formulae 
> (for more on this there is a website [here](https://www.geol.lsu.edu/jlorenzo/geophysics/uncertainties/Uncertaintiespart2.html)). For example, if we are
> adding two quantities together ($Z=X+Y$) the standard error $\Delta Z$ can be calculated using the relation $(\Delta Z)^2 = (\Delta X)^2 + (\Delta Y)^2$
>
> Write a function which calculates the perimeter of an equilateral triangle and the standard error associated with this perimeter. 
> The function argument will specify the length of the triangle sides and the uncertainty associated with each measurement.
> 
> > ## Solution
> >
> > ~~~
> > def perimeter_error(length, uncertainty):
> >     perimeter = length + length + length
> >     perimeter_error = math.sqrt(uncertainty**2+uncertainty**2+uncertainty**2)
> >     return perimeter, perimeter_error
> > ~~~
> > {: .python}
> {: .solution}
{: .challenge}

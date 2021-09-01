# Lab 2: Super Math Bros

In this lab, you will learn how to:
- style code correctly
- use `string`, `int` and `float` variables
- do integer and float arithmetic in c++

## Question 1: wario.cpp

Wario, a foreign spy, has infiltrated our codebase and messed around with the styling of our code! Everything still works, but the code is now almost impossible to read! Help us clean it up before our friend Luigi gets confused.

#### 1. There should be no more than one blank line between two lines of code.

Do you see any large blank gaps in the `wario.cpp` program? Remove those empty lines.

**Example:** This code is good because there is at most one empty line between any two lines of code:
```
int main() {
  int x = 1;
  
  cout << x << endl;
  return 0;
}
```
This code is not okay because there is a gap of 2 empty lines:
```
int main() {
  int x = 1;
  
  
  cout << x << endl;
  return 0;
}
```

#### 2. Code should be indented consistently.

Right now, our code is relatively simple, so here's what this rule actually means:

Every line between `int main() {` and `}` should start with **2 spaces**.
(Later on in the course, this rule will become more complex.)

By default, you can do this in Replit
just by hitting the tab key once. It will automatically appear as 2 spaces.

Fix the code's indentation now.

**Example:** This code is okay because everything is indented by 2 spaces:
```
int main() {
  int x = 1;
  int y = 2;
  
  cout << x << endl;
  cout << y << endl;  
  cout << x + y << endl;
  
  return 0;
}
```
This code is not okay - the indentation is all over the place:
```
int main() {
                int x = 1;
    int y = 2;
  
          cout << x << endl;
  cout << y << endl;  
cout << x + y << endl;

        return 0;
}
```

#### 3. Semicolons go at the end of statements and each statement should be on its own line.

What does this actually mean?
* You should not have a semicolon at the start of a line or in the middle of a line (for now).
* You should not have multiple semicolons per line (for now).
* You should not have a semicolon all alone on a line doing nothing.

Do you see any misplaced semicolons? Fix those in the code by putting them in the right spot.

**Example:** This code is okay because every line ends in a semicolon and there are no semicolons at the beginning or middle of lines:
```
int main() {
  int x = 1;
  int y = 2;
  
  cout << x << endl;
  cout << y << endl;
  cout << x + y << endl;
  
  return 0;
}
```
This code is not okay - there are lots of semicolons in bad places:
```
int main() {
  int x = 1; int y = 2;
  ;
  cout << x << endl
  ;cout << y << endl; cout << x + y << endl
  ;return 0;
}
```

#### 4. Whenever we use a symbol like `=` or `+` or `<<`, put spaces around it.

There should be exactly one space on each side.
This applies to all of the operators that we have learned: `>> << = + - * / % += -= *= /= %=`

**Example:** The following code is good because there are spaces before and after all the symbols:
```
int main() {
  int x = 1;
  int y = 0;
  y += x;
  int z = x + y - 2;
  cout << x << endl;
}
```
The following code is not okay because everything is smushed together and hard to read or there are too many spaces:
```
int main() {
  int x =1;
  int y=0;
  y+=x;
  int z =           x   +y-2;
  cout <<x<<                  endl;
}
```

#### 5. There should be no TODO comments in the code when you are done.

We've had this rule since Lab 0.

The reason we should remove TODO comments is that a TODO comment means "I need to do this in the future."

If you already did what the comment said, but you left the TODO comment in, it's confusing and it takes up unnecessary space.
And if you didn't do what the comment said, that means your code isn't done!

Remove all TODO comments in the code now. The word TODO should never appear in your submitted code.

### Expected output

You shouldn't be changing anything the code does. When you compile (`g++`) and run (`./a.out`) the program, your terminal should look exactly like this:
```
$ ./a.out 
Hi!
x = 7
$
```

### Notes on autograder

From now on, autograder will check if your code complies with our style rules. You should now see the following test types:
* **Compilation test:** Whether your code successfully compiled
* **TODO check:** The autograder will tell you if you forgot to remove the TODOs
* **(NEW) Style check:** Checks to see if your code follows our style rules.
* **Output and/or exit code tests:** Checks to see if your code does the right thing

Here's an example error message from autograder and how to interpret it:
```
Input: 
*** Expected Output
--- Your Program's Output
***************
*** 1,7 ****
- x = 1
  x = 1, y = 7
  x = 3, y = 7
  x = 3, y = 6
  x = 7, y = 6
  food = bread
! food = water
--- 1,7 ----
  x = 1, y = 7
+ I'm an extra line!
  x = 3, y = 7
  x = 3, y = 6
  x = 7, y = 6
  food = bread
! food = definitely not water
```

* `Input`: If there is nothing written after "Input:" then there was no input to your program. If there is something, it's what the autograder typed in when the program was run.
* `*** Expected Output`: This means that the next section, the one with `*** 1,7 ****` above it, is what the output should be. `1,7` means it is showing you lines 1-7 of the output. The autograder will always show you the full output for test cases. It will show only some of the lines in your code for style checks and these line numbers will help you find where the problem is.
* `--- Your Program's Output`: This means that the bottom section, the one after `--- 1,7 ----` is what your program's output was. The numbers also indicate line numbers.
* The first two characters on any line (`! `, `+ `, `- `, or `  `) are not part of the output of your program. These characters help you figure out what lines are wrong:
    * `! `: This means that the lines in the two outputs are different. 
      In this example, the last line should be `food = water` but our program output something different so there's an exclamation point next to the two different lines. **BE CAREFUL OF WHITESPACE DIFFERENCES.**
    * `- `: If this appears next to a line in the top section, it's missing in the bottom.
      In this example, the expected output has `x = 1` as the first line, but your program is missing it.
    * `+ `: If this appears next to a line in the bottom section, it's not in the top section.
      In this example, your program's output has an extra line (`I'm an extra line!`) so that line is marked.
    * `  ` (two spaces, no symbols): The lines are the same in both sections. This means this line is correct.

**TL;DR**: Look at the symbols to figure out where your code differs from the expected output.

**Note**: Your code should never print out the symbols in output. The symbols are printed by the autograder to help you quickly find the mistakes.

### Grading

* 1 point for compiling properly
* 1 point for removing all TODOs
* 10 points for complying to coding style rules
* 3 points for the program behaving properly

## Question 2: luigi.cpp

Oh no, the toilet is broken! You call up your plumber friend, Luigi, but he is currently out of town. He did however provide you with a set of instructions on how to fix the pipes by yourself.

#### Luigi's Pipeline to Healthy Pipes

1. Use `setprecision` to print floats with 1 digit after the decimal point.
    - This has already been done for you, courtesy of Luigi.
1. Declare an `int` variable named `drill_setting` that is initialized to 1.
    - This has also been done for you, courtesy of Luigi.
1. Declare a `float` variable named `power_level` that is initialized to 7.
1. Use `cout` to print out `drill_setting` and `power_level` according to the following pattern:
  ```
  drill_setting = <VALUE OF drill_setting>, power_level = <VALUE OF power_level><END OF LINE>
  ```
  The output should look like this, on its own line:
  ```
  drill_setting = 1, power_level = 7.0
  ```
1. Assign `drill_setting` the value of 3.
1. Print out `drill_setting` and `power_level` again the same way.
1. Assign `power_level` the value of 6.5.
1. Print out `drill_setting` and `power_level` again the same way.
1. Assign `drill_setting` the value of `power_level + 1`.
1. Print out `drill_setting` and `power_level` again the same way.
1. Declare an `int` variable named `battery` that is initialized to `10 - (int)power_level / 2`.
1. Declare a `string` variable named `status` that is initialized to `"fixing"`.
1. Print out `battery` and `status` according to the following pattern:
  ```
  battery = <VALUE OF battery>, status = <VALUE OF status><END OF LINE>
  ```
  The output should look like this, on its own line:
  ```
  battery = 7, status = fixing
  ```
1. Decrease the value of `battery` by 1.
1. Assign `status` the value of `"fixed"`.
1. Print out `battery` and `status` again the same way.

Follow these instructions and make necessary code changes in `luigi.cpp`. Don't forget to style your code according to guidelines described in question 1!

### Expected output

Check to make sure that your program's output in the terminal looks exactly like this. If it doesn't, the autograder will mark you wrong:
```
$ ./a.out
drill_setting = 1, power_level = 7.0
drill_setting = 3, power_level = 7.0
drill_setting = 3, power_level = 6.5
drill_setting = 7, power_level = 6.5
battery = 7, status = fixing
battery = 6, status = fixed
$ 
```

### Grading

* 1 point for compiling properly
* 1 point for removing all TODOs
* 3 points for complying to coding style rules
* 10 points for the program behaving properly

## Question 3: toad.cpp

Toad, your racer friend, boasts about their performance all the time. They always tell you their time in seconds, which can be hard to reason about.

Write the `toad.cpp` program to convert the number of seconds that the user inputs into time in hours, minutes, and seconds. Don't forget to style your code according to guidelines described in question 1!

For example:
* If the input is `63` then the output will be `0 hour(s), 1 minute(s), and 3 second(s)` because 63 seconds is 1 minute and 3 seconds.
* If the input is `3600`, then the output will be `1 hour(s), 0 minute(s), and 0 second(s)` because there are 3600 seconds in an hour.
* If the input is `13530` then the output will be `3 hour(s), 45 minute(s), and 30 second(s)` because 13,530 seconds is that much time.

This might sound like a really complicated task, but we can break it down into some smaller tasks.

### Look at the starter code

There is already some starter code in this file. What does this code do?

The code prints out "Enter a number of seconds:" on its own line.

Then, it declares a variable of type `int` called `seconds` and sets its value to be whatever the user typed in.

Then, it declares a variable of type `int` called `minutes` and initializes it to 0.

Then, it declares a variable of type `int` called `hours` and initializes it to 0.

Finally, it prints out the values of all three variables in the format `X hour(s), X minute(s), and X second(s)` where the X's are replaced with the value of the correct variables.

### Think about how to solve a smaller problem

Let's ignore the hours for now and focus on just minutes and seconds.

If someone asked you how to convert seconds to minutes and seconds, how would you do it?

Make sure you can answer this question in words - don't try to type any code yet.

### Translate the solution into code

The starter code already has a variable named `minutes` declared for you. 

How do you set the values of `minutes` and `seconds` so that they represent how many minutes and seconds there are? 
(You should ignore `hours` for now)

**Hint**: The arithmetic operations you can use in C++ are `+ - * / %`. In lecture, we talked about what integer division is. To do integer division in C++, we use `/`. Maybe the modulus operator `%` will be helpful too...

### Compile, run, and test your program.

Give it some different test inputs and see if the output matches what you expect. 

If it's not working, edit your code until this part works. You should ignore the hours part for now, just focus on whether it says the correct number of minutes and seconds.

### Now solve the original problem

Once your program converts seconds to minutes and seconds correctly, answer the question: if someone asked you to convert minutes to hours and minutes, how would you do it? Again, don't go to the next step until you can answer this question.

Now, translate that into code. The starter code already has a variable named `hours` declared for you. Set the values of `hours` and `minutes` to represent how many hours and minutes there are.

Compile, run, and test your program. Try different inputs to make sure your code works on all the inputs.

Once your code is working, congrats! You came up with an **algorithm**, or a way to solve a problem. Then, you implemented that algorithm by writing code that uses that method of solving the problem.

In this case, you thought of an algorithm to convert time in seconds to time in hours, minutes, and seconds. You also broke down the problem into smaller pieces (writing code to convert to just minutes and seconds first, then to hours, minutes, and seconds).
This is a good problem-solving strategy that you can use in the future.

### Grading

* 1 point for compiling properly
* 1 point for removing all TODOs
* 3 points for complying to coding style rules
* 10 points for the program behaving properly

## Question 4: bowser.cpp

Your friend Bowser got bored and invited you to his castle to do math questions. However, he is super fast and you cannot keep up with the speed at which he is answering those questions. You decide to write a program to answer them for you.

Write the `bowser.cpp` program that does the following. Don't forget to style your code according to guidelines described in question 1!

1. Look at the line in your starter code that says `cout << setprecision(1) << fixed;` and change it so that your program will print floats with `2` digits after the decimal point. 
1. Declare two `int` variables named `x` and `y`.
1. Print out "Enter an integer x:" followed by a newline.
1. Store what the user inputs on `cin` in `x`.
1. Print out "Enter a non-zero integer y:" followed by a newline.
1. Store what the user inputs on `cin` in `y`.
1. Print out "x + y = " followed by the value of x + y followed by a newline
1. Print out "x - y = " followed by the value of x - y followed by a newline
1. Print out "x * y = " followed by the value of x * y followed by a newline
1. Print out `x / y = <value> or <value> remainder <value>` followed by a newline.
  
  The three values (in order) are:
    * The result of float division of `x / y`
    * The result of integer division of `x / y`
    * The remainder of `x / y`
  
**Hint**: You might need to cast something.

### Casting
When you **cast** something from one type to another, you are converting it from one type to another. We write the new type in parentheses before an expression in order to cast.

**Example**: If we have an `int` stored in a variable, but we want to get the same number as a decimal, we can cast it to a `float`. Here, we cast `x` to a `float` and store the result in `y`.
Now the value of `y` is `1.0`.
```
int x = 1;
float y = (float)x;
```
We can also cast the other way around, from a `float` to an `int`. When we go from `float` to `int`, the part after the decimal is dropped (just like how integer division drops things after the decimal point). In this example, the value of `x` is `17`.
```
float y = 17.8;
int x = (int)y;
```
You can use casting as part of a more complicated expression:
```
int x = 2;
float y = 18.7 / (int)(x + 3.14159);
cout << (int)y << endl;
```

### Example expected output

If you run your program and give it the inputs `7` and `3`, your terminal should look exactly like:
```
$ ./a.out
Enter an integer x:
5
Enter a non-zero integer y:
2
x + y = 7
x - y = 3
x * y = 10
x / y = 2.50 or 2 remainder 1
$
```

### Grading

* 1 point for compiling properly
* 1 point for removing all TODOs
* 3 points for complying to coding style rules
* 10 points for the program behaving properly

## Rubric

* (60 points) Programming
    * (15 points) for each of the `wario`, `luigi`, `toad` and `bowser` programs
* (40 points) Written assignment - see Gradescope for point breakdowns

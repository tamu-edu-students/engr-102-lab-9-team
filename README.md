# ENGR 102 Lab Topic 9 (team)
There is only one deliverable for this team assignment. Please submit the following file to Gradescope. Please include the team header information at the top of your file with the names of all contributing team members. This is a team assignment, but **everyone** must submit the file for credit. You may discuss the problems with other teams, but your submitted work must be unique. Check out the [Frequently Asked Questions](#frequently-asked-questions) below.

## Activities

1. [Word Puzzle](#word-puzzle)

## Word Puzzle
This activity will help you practice writing functions while checking a solution to a word puzzle. 

Word Arithmetic: This is a long-division problem in which letters are substituted for numbers.

```
          RUE        
      _______        Dividend = Quotient * Divisor + Remainder
 EAR | RUMORS        RUMORS   = RUE      * EAR     + USA
       UEII  
       ------        To solve the problem, determine the number value
        UKTR         of each letter. When the letters used in the puzzle
         EAR         are arranged in order from 0 to 9, they will spell
         ----        out a word or words (no spaces).
         KEOS
         KAIK          ----------
         ----          0123456789
          USA
```
**[You are given Python starter code for this activity.](word_puzzle.py)** In this file you are given a string representing a puzzle and a function to print the puzzle as a long division problem (as shown above). The example puzzle string is hardcoded for now, but will be taken in as a user input later. For the puzzle shown above, the puzzle string is:
```
RUE,EAR | RUMORS,UEII  ,UKTR ,EAR ,KEOS,KAIK,USA
```
Notice that in addition to letters, the puzzle string contains spaces, commas, and the vertical line character `|`.

Create a program named `word_puzzle.py` that allows the user to check an answer for a given word arithmetic puzzle via the following steps:
1. Create a function named `get_valid_letters` that takes in as an argument one string representing a puzzle and returns one string of ten (10) unique letters found in the puzzle. For the example puzzle above, your function should return the string `RUEAMOSIKT`.

2. Create a function named `is_valid_guess` that takes in as arguments two strings and returns a Boolean value. The first string passed to the function is the string of valid letters from step 1; the second string is a guess from the user. The function should return `True` only if the user's guess string contains **exactly** 10 unique letters from the valid letters string. This function does NOT check if the user’s guess is the correct solution to the puzzle. For example, if the user’s guess is `TAKEOURSIM` or `IMAKETOURS`, the function returns `True`; if the user’s guess is `IMAKEIMAKE`, `TAKEOUR`, `TAKEOURSIMM`, or `TAKEOURSBD`, the function returns `False`.

3. Create a function named `check_user_guess` that takes in as arguments four integers representing the dividend, quotient, divisor, and remainder (in that order) and returns a Boolean value. The function should return `True` only if the following equation holds:
```
Dividend = Quotient * Divisor + Remainder
```
Otherwise, the function should return `False`.

4. Create a function named `make_number` that takes in as arguments two strings and returns one integer. The first string passed to the function contains a word to be converted to an integer; the second string is the user’s guess which should be used as a key to convert a word (the first string) to its integer equivalent. For example, if the word is `RUE` and the user’s guess is `TAKEOURSIM`, the integer equivalent of `RUE` is `653`.
```
  TAKEOURSIM
  ----------
  0123456789
```

5. Create a function named `make_numbers` that takes in two arguments, both of which are strings, and returns a tuple of four integers. The first string passed to the function is the puzzle string; the second string is the user’s guess. Your `make_numbers` function should call your `make_number` function four times to create the four integers, and then should return a tuple of those four values that are the equivalent integers of the words representing the dividend, quotient, divisor, and remainder (in that order). For the puzzle example shown above and the user guess `TAKEOURSIM`, your function should return `(659467, 653, 316, 571)`.

6. Create a function named `main` that does not take in any arguments nor return any values. This function should take as input from the user a puzzle string, print the puzzle, ask the user to enter a guess, and output an appropriate message. **Do not ask the user to enter a second guess.** Your `main` function should call your `get_valid_letters`, `is_valid_guess`, `make_numbers`, and `check_user_guess` functions, as well as the provided `print_puzzle` function. Format your output as shown below.

7. Finally, in your main code type the following:
```python
if __name__ == "__main__":
    main()
```
You should **NOT** include any other executable lines in your main code.

Example beginning output for ALL cases (using input `RUE,EAR | RUMORS,UEII  ,UKTR ,EAR ,KEOS,KAIK,USA` for the puzzle string):
```
Enter a word arithmetic puzzle: 
RUE,EAR | RUMORS,UEII  ,UKTR ,EAR ,KEOS,KAIK,USA

             RUE
         _______
    EAR | RUMORS
          UEII  
          ------
           UKTR 
            EAR 
            ----
            KEOS
            KAIK
            ----
             USA
```

Example output (using the same puzzle string as above and `TAKEOURSIM` for the user’s guess (**valid and wrong**)):
```
<output from above>

Enter your guess, for example ABCDEFGHIJ: TAKEOURSIM 
Try again! 
```

Example output (using the same puzzle string as above and `TAKEOUR` for the user’s guess (**invalid**)):
```
<output from above>

Enter your guess, for example ABCDEFGHIJ: TAKEOUR 
Your guess should contain exactly 10 unique letters used in the puzzle. 
```

Example output (using the same puzzle string as above and a **valid and correct** user’s guess):
```
<output from above>

Enter your guess, for example ABCDEFGHIJ: <correct guess> 
Good job! 
```

**Hint:** You may find it easier to hardcode a puzzle string when testing your code. When you have debugged your code, replace the puzzle string with an input statement.



## Frequently Asked Questions
1. **Do I have to actually solve the word-math puzzles?** No! Unless you want to for fun, of course! The code you are writing will check a guess from the user, it won't solve the puzzles.

2. **How do I split a string of <stuff> into a list again?** Remember what you did in [LAB: Topic 7 (individual)](https://github.com/tamu-edu-students/engr-102-lab-7-individual)? That's right, you used `mystr.split()`. If you don't put anything inside the `()`, it will default split on the spaces. But how do you split on the commas? You can specify which character to split on! For example:
```python
mystr = 'A,B,C,D,E'
mylist = mystr.split(',')
```
will produce the list `['A', 'B', 'C', 'D', 'E']`.

3. **Do I have to name my functions exactly as the lab document says?** Yes! For the autograding to work, it's going to import your file and call your functions. If you use a different name for one of your functions, the autograding code won't find it, which means you won't get any points. :(

4. **What does the stuff in the main code mean?** You mean this?
```python
if __name__ == "__main__":
    main()
```
Short answer: it makes writing the autograding code much easier.

Long answer: it prevents the autograder from accidentally running your code when it imports your file. When you import a module in python, the interpreter actually runs the code. Modules usually only have function definitions and sometimes constants; they're not meant to be programs that do something. I want your program to do something, but I also want to import your functions for unit testing (testing a function on its own). When you run a python file, python automatically gives the file the name `"__main__"`. When you import a file, it doesn't get the name `"__main__"`. So if I run your file directly, it calls your `main()` function, but if I import your file, it won't. Try this. Create a new file named `apple.py`, add the following code, and run it.
```python
if __name__ == "__main__":
    print("apple pie yum yum")
elif __name__ == "apple":
    print("YOU IMPORTED apple.py!!!")
```
You should see `apple pie yum yum` in the console. Now, create another new file named `blueberry.py`, add the following code, and run it. 
```python
import apple
print("blueberry pie ftw")
print(f"name of this file: {__name__}")
```
Now you should see:
```
YOU IMPORTED apple.py!!!
blueberry pie ftw
name of this file: __main__
```
Cool, huh? Also, **you absolutely don't need to know this for this class and you will not be tested over it**. But if you're interested, [Runestone Academy also has an explanation](https://runestone.academy/ns/books/published/ENGR_102_OER/Functions/mainfunction.html).

Have a question you don't see here? Email your instructor!

Based on Dell Official Variety Puzzles (February 2016)<br/>
Revised Summer 2026 SNR

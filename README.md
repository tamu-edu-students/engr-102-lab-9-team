# ENGR 102 Lab Topic 9 (team)
There is only one deliverable for this team assignment. Please submit the following file to Gradescope. Please include the team header information at the top of your file with the names of all contributing team members. This is a team assignment, but **everyone** must submit the file for credit. You may discuss the problems with other teams, but your submitted work must be unique. Check out the [Frequently Asked Questions](#frequently-asked-questions) below.

## Activities

1. [Word Puzzle](#word-puzzle)

## Word Puzzle
The

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
Cool, huh? Also, you absolutely don't need to know this for this class and you will not be tested over it.

Have a question you don't see here? Email your instructor!

Based on Dell Official Variety Puzzles (February 2016)<br/>
Revised Summer 2026 SNR

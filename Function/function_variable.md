

###  Functions & Variables

-----

#### **The First Program: "hello, world"**

The most basic program is just one line. It goes in a `.py` file.

```python
print("hello, world")
```

To run it, you go to the terminal and type:

```bash
python hello.py
```

  * **Function**: An action, like `print`.
  * **Argument**: The input you give the function, like `"hello, world"`.
  * **Side Effect**: What the function actually does, like showing text on the screen.
  * **Bug**: A mistake. A typo like forgetting a parenthesis is a `SyntaxError`.

*Important: Don't use Microsoft Word or Google Docs. They add weird formatting. Use a text editor like VS Code.*

-----

#### **Getting Input with Variables**

To make the program interactive, you need to get input from the user.

```python
# input() asks the user a question and waits for them to type.
# The text they type is stored in the 'name' variable.
name = input("What's your name? ")

# Then we can use the variable.
print("hello, " + name)
```

  * **`input()`**: This function gets text from the user.
  * **Return Value**: `input()` *returns* whatever the user typed. It's always a string.
  * **Variable**: A placeholder to store a value, like `name`.
  * **Assignment (`=`)**: The equals sign isn't for math here. It means "take the value on the right and put it in the variable on the left".

-----

#### **Working with Strings (Text)**

A "string" (`str`) is just a piece of text. You can use methods to change them. Methods are functions that belong to a specific type of data, accessed with a dot.

```python
name = input("What's your name? ")

# Clean up the input.
# .strip() removes spaces from the beginning and end.
# .title() capitalizes the first letter of each word.
# You can chain them together.
name = name.strip().title()

# Use an f-string to print it out.
print(f"hello, {name}")
```

**F-strings** are the best way to put variables inside strings. Just put an `f` before the first quote and wrap variables in `{}`. It's much cleaner than joining with `+`.

-----

#### **Working with Numbers (int & float)**

  * `int`: An integer, or whole number (like 5, -10, 0).
  * `float`: A number with a decimal point (like 1.5, 3.14).

**This is critical:** `input()` always gives you a **string**, even if the user types a number. You *must* convert it if you want to do math.

```python
# This will NOT work as expected. If you type 1 and 2, it prints "12".
x = input("What's x? ")
y = input("What's y? ")
print(x + y) # Wrong. This just joins the strings.

# This is the correct way. Convert to numbers first.
x = int(input("What's x? "))
y = int(input("What's y? "))
print(x + y) # Correct. This adds the numbers.
```

Math operators are what you'd expect: `+`, `-`, `*`, `/`.
`**` is for exponents (like $2^3$ is `2 ** 3`).
`%` gives the remainder of a division.

-----

#### **Making My Own Functions**

Instead of repeating code, you can bundle it into your own function.

  * `def` is the keyword to **def**ine a function.
  * **Indentation** (the spaces) is how Python knows what code is inside the function. **It is not optional.**
  * `return` sends a value back from the function.

<!-- end list -->

```python
# The main logic of the program
def main():
    x = int(input("What's x? "))
    print("x squared is", square(x))

# A custom function I made
def square(n):
    # This function returns n*n
    return n * n

# This line actually runs the code in main()
main()
```

  * **Parameter**: The name of the input inside the function definition (like `n`).
  * **Argument**: The actual value you pass to the function when you call it (like `x`).
  * **Scope**: A variable created inside a function only exists inside that function. `n` doesn't exist outside of the `square` function.

-----

#### **How to Structure a Program**

It's good practice to organize your code so it's easy to read.

1.  Put your main code into a function called `main()`.
2.  Define any other "helper" functions you need (like `square`).
3.  At the very end of the file, add one line to call `main()`.

This structure lets you define your functions in any order, because nothing actually runs until `main()` is called at the end.
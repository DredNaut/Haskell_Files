# Starting out 

GHCI is used for compiling and running Haskell code.
To start using the GHCI compiler just type the following command in the terminal. (Make sure it is installed first.)

> ghci

or if you want a custom prompt, type the following

: set prompt "blah-blah> "

#### Arithmetic
Multiple arithmetic operations can be performed from within the ghci compiler. The following are examples of some of the arithmetic that can be performed:

> 2 + 15
> 48 * 3
> 12 / 6
> 12 - 6

#### Boolean Logic
Like most other programming synatax you can apply parentheses to group equations together and change the precedence of the operations.

This interpreter allows you to evaluate boolean expressions aswell:

> True && False
> False || True
> not False

#### Testing for Equality
You can test for equality in the following way:

> 5 == 5
> 1 /= 0
> "Hello" == "Hello"

But just as a note you cannot use this across different data types

#### Various Functions
If you are incrementing something you can use the following built-in function:

> succ 8

Or if you are looking for the max and the min of a data set then you can use the following commands:

> min 9 10
> max 3.4 3.2

For example the following expression is a bit more complicated, but not too bad:

> (succ 9) + (max 5 4) + 1
16

Next will be an example of infix format for a given function:
We will be using the div function which takes two numbers and performs integer division on them.

> 92 `div` 10 
9



















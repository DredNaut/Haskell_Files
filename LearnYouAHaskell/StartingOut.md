# Starting out 

GHCI is used for compiling and running Haskell code.
To start using the GHCI compiler just type the following command in the terminal. (Make sure it is installed first.)

```
> ghci
```

or if you want a custom prompt, type the following

```
: set prompt "blah-blah> "
```

### Arithmetic
Multiple arithmetic operations can be performed from within the ghci compiler. The following are examples of some of the arithmetic that can be performed:

```
> 2 + 15
> 48 * 3
> 12 / 6
> 12 - 6
```

### Boolean Logic
Like most other programming synatax you can apply parentheses to group equations together and change the precedence of the operations.

This interpreter allows you to evaluate boolean expressions aswell:

```
> True && False
> False || True
> not False
```

### Testing for Equality
You can test for equality in the following way:

```
> 5 == 5
> 1 /= 0
> "Hello" == "Hello"
```

But just as a note you cannot use this across different data types

### Various Functions
If you are incrementing something you can use the following built-in function:

```
> succ 8
```

Or if you are looking for the max and the min of a data set then you can use the following commands:

```
> min 9 10
> max 3.4 3.2
```

For example the following expression is a bit more complicated, but not too bad:

```
> (succ 9) + (max 5 4) + 1
16
```

Next will be an example of infix format for a given function:
We will be using the div function which takes two numbers and performs integer division on them.

```
> 92 `div` 10 
9
```

### Creating Functions
We will now create a function in which we will double the input of the function and return it as output, for this particular example the code will be written in a file with the extension .hs:

```
doubleMe x = x + x
```

The function doubleMe takes as in put one parameter called x and returns the output 'x + x'.

So now lets make another function which takes two parameters as input, and returns the doubled sum of both.

```
doubleUs x y = x*2 + y*2
```

### Adding Complexity
Let us now create another function which uses conditionals to change determine the output of the function.

```
doubleSmallNumber x = if x > 100
                        then x
                        else x*2
```

So this function now will double the number if the given input is less than 100.

### Introduction to Lists
Now we will practice generating a few lists to mess around with.
Notice that we are using 'let' to define a name inside of GHCI

```
ghci> let lostNumbers = [4,8,15,16,23,42]
ghci> lostNumbers
[4,8,15,16,23,42]
```
#### List Operations
To put two lists together we will use the '++' operator:

```
ghci> [1,2,3,4] ++ [9,10,11,12]
[1,2,3,4,9,10,11,12]
ghci> "hello" ++ " " ++ "world"
"hello world"
```

On the other hand we can append single characters to the list by using the ':' operator.

```
ghci> 5:[1,2,3,4,5]
[5,1,2,3,4,5]
```

We can play around with prepending elements to an empty list:
1:2:3:[] = [1,2,3]

Lists my contain lists of lists in the following way:
[] and [[]] and [[],[],[]]

By using the '!!' operator you can pull off the value at n index.
```
ghci> "Steve Buscemi" !! 6
'B'
ghci> [9.4,33.2,96.2,11.2,23.25] !! 1
33.2
```
















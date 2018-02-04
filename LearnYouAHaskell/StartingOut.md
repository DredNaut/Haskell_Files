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
#### List Comparisons
We can compare lists that same way we compare numbers and strings.
By using '>, <, =='

```
ghci> [3,2,1] > [2,1,0]
True
ghci> [1,2,3] < [3,4,6]
True
ghci> [3,4,2] == [3,4,2]
```
#### Basic List Functions
```
ghci> head [5,4,3,2,1]
ghci> tail [5,4,3,2,1]
ghci> last [5,4,3,2,1]
ghci> init [5,4,3,2,1]
ghci> length [5,4,3,2,1]
ghci> null [1,2,3]
ghci> reverse [5,4,3,2,1]
ghci> take 3 [5,4,3,2,1]
ghci> drop 3 [8,6,4,2]
ghci> minimum [8,4,2,1,5,6]
ghci> maximum [1,9,2,3,4]
ghci> sum [5,2,1,6,3,2,5,7]
ghci> product [1,2,3,4,5,6]
ghci> 4 `elem` [2,3,4,5]
```
#### List ranges, cycles, repeat, and replicate
To generate a range use the '..' in between the list brackets. 
```
ghci> [1..20]
[1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20]
```
To create a cycle which is an infinite loop of the same list, you should always use take to split the list. 
```
ghci> take 10 (cycle [1,2,3])
[1,2,3,1,2,3,1,2,3,1]
```
We can create a list of a certain pattern by using the repeat function in conjunction with the take function.
```
ghci> take 10 (repeat 5)
[5,5,5,5,5,5,5,5,5,5]
```
And lastly we can use the function replicate to quickly make a list of one number.
```
ghci> replicate 3 10
[10,10,10]
```

### List Comprehension
Using the following we can create a list with the set of the first 10 even natural numbers.
```
take 10 [2,4..]
```
We can do the same thing using a list comprehension
```
[x*2 | x <- [1..10]]
```
Now we can add a predicate to that previous comprehension, predicates after binding parts are separated by a comma.
```
[x*2 | x <- [1..10], x*2 >= 12]
```
This comprehension will result in the elements 1-10 which doubled yeild a value greater than 12
```
[x | x <- [10..20], x /= 13, x /=15, x /= 19]
```
We can also do list multiplication in the following way
```
[x*y | x <- [2,5,10], y <- [8,10,11]]
```
List comprehensions that combines a list of adjectives and a list of nouns
```
let nouns = ["hobo","frog","pope"]
let adjectives = ["lazy","grouchy","scheming"]
[adjective ++ " " ++ nouns | adjective <- adjective, noun <- nouns]
```
#### Tuples
Tuples are a way to represent a two dimensional vector in Haskell, and a tuple can contain a combination of several types.
**fst** takes a pair and returns its first complement.
```
ghci> fst (8,11)
8
```
**snd** takes a pair and returns its second component.
```
ghci> snd (8,11)
11
```
**zip** takes two lists and zips them together into one list by joining the matching elements into pairs.
```
ghci> zip [1..5] (take 5 (repeat 5))
[(1,5),(2,5),(3,5),(4,5),(5,5)]
```
To find a list of right triangles we can use the following list comprehension.
```
[ (a,b,c) | c<- [1..10], b <- [1..10], a <- [1..10], a^2 + b^2 == c^2]
```

This concludes the **starting out** tutorial.









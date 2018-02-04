# Syntax In Functions
### Pattern Matching
We can make a function that checks if the number we supplied to it is a seven or not.
```
lucky :: (Integral a) => a -> String
lucky 7 = "LUCKY NUMBER SEVEN!"
lucky x = "Sorry, you're out of luck, pal!"
```
In the following way we defined the ways the functioon should react to certain types of input.
Lets make another function which has more than two parameters now.
```
sayMe :: (Integral a) => a -> String
sayMe 1 = "One!"
sayMe 2 = "Two!"
sayMe 3 = "Three!"
sayMe 4 = "Four!"
sayMe 5 = "Five!"
sayMe x = "Not between 1 and 5"
```
Of course these statements can not be in any order because there is a precedence to the output, starting from the top moving to the bottom.
#### Factorial Function
Let's try something a little more interesting, like computing factorials. This next function uses recursion to compute the factorial of a number.
```
factoral :: (Integral a) => a -> a
factorial 0 = 1
factorial n = n * factorial (n - 1)
```
#### Adding Vectors
The next function will demonstrate the usefulness of pattern matching as we can use any character that we wish.
```
addVectors :: (Num a) => (a,a) -> (a,a) -> (a,a)
addVectors (x1, y1) (x2, y2) = (x1 + x2, y1 +y2)
```
#### Ignored Parameters
We can use the '_' character to show that we do not care what that particular input is because we are not going to use it in any meaningful way.
```
first :: (a, b, c) -> a
first (x, _, _) = x
second :: (a, b, c) -> b
second (_, y, _) = y 
third :: (a, b, c) -> c
third (_, _, z) = z
```
These functions allow use to find the first second and third values for triples.








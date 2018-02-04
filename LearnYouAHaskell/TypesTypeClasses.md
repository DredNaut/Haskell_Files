# Types and Typeclasses

### Believe the type
In Haskell a static type system is used, meaning that the type of every expression is known at compile time.
Haskell also has type inference meaning that if we type a number Haskell can infer it is a number on its own.
A tpye tells us which category of things that expression fits.
EX. ```True``` is a boolean, ```"hello"``` is a string
We can use the ```:t``` command which, followed by and valid expression, tells us its type.
```
ghci> :t 'a'
'a' :: Char
ghci> :t True
True :: Bool
ghci> :t "HELLO!"
"HELLO!" :: [Char]
ghci> :t (True, 'a')
(True, 'a') :: (Bool, Char)
```
The double colon operator '::' is read as "has the type of". Explicit types are denoted with the firest letter in capital.
Functions also have types and from here on we will always give type declarations to our functions.
Lets make a function the filters a string so that only caps remain.
```
removeNonUppercase :: [Char] -> [Char]
removeNonUppercase st = [c | c <- st, c `elem` ['A'..'Z']]
```
This function has the type of **[Char] -> [Char]** meaning that it maps from a string to a string. The **[Char]** type is synonymous with **String** so it's clearer if we write
```
removeNonUppercase :: String -> String
```
### Typesclasses 101
What is the type signature of ```==```
```
ghci> :t (==)
(==) :: (Eq a) => a -> a -> Bool
```
The equality operator is a function.

```Eq``` is used for types that support equality testing
Mainly for '==' or '/='
```Ord``` is for types that have an ordering
```
ghci> :t (>)
(>) :: (Ord a) => a -> a -> Bool
```

Ordering can be Greater than, Less then, and Equal to respectively.

**show** will present the input as a string.
```
ghci> show 3
"3"
ghci> show 5.334
"5.334"
ghci> show True
"True"
```
**Read** is the oposite of show. The read function takes a string and returns a type which is a member of Read.
```
ghci> read "True" || False
True
ghci> read "8.2" + 3.8
12.0
ghci> read "5" - 2
3
ghci> read "[1,2,3,4]" ++ [3]
[1,2,3,4,3]
```
### Type Annotations
We can use type annotations to say which type we want the read to be. Read will only produces a valid output if the input of the functions specifies a second operatoin which would give an idea of which type it wanted to produce.
For specifying type use '::'
```
ghci> read "5" :: Int
5
ghci> read "5" :: Float
5.0
ghci> (read "5" :: Float) * 4
20.0
ghci> read "[1,2,3,4]" :: [Int]
[1,2,3,4]
ghci> read "(3, 'a')" :: (Int, Char)
(3, 'a')
```


















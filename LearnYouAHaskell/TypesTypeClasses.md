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

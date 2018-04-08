# Haskell Notes (Cheat sheet)

## GHCI
| Command	| Description
|---			|---
|:type		| Gives the type of the function
|:info		| Information about the function
|:q			| Quit


## Numbers 
| Function 	| Description								| Example
|-----------|-----------------------------------|----------
| odd 		| Determines if number is odd 		| `odd 2`  
| even 		| Determines if number is even 		| `even 2` 
| ^ 			| Power of 									| `2^4`

---------------------------------------------------------------

## Definitions / Terms
| Term							| Definition													| Example
|---								|---																|---
| type constructor			|																	| `data NullBool = Nothing | False | True`
| type value constructor	| 																	| `data Thing = Thing { first :: string, second :: Int }` 
| type synonym					| alternative definition for a type 					| type String = [Char]

## Expressions and Clauses

### Where clause

A `where` clause can be placed after a function to bind intermediate results
or define intermediate functions. It does not apply across pattern matches

### Let expressions

A `let` expression binds variables locally to an expression. They take the form

`let` &lt;bindings&gt; `in` &lt;expression&gt;

They can be used anywhere an expression is required.

### Case expression

`case` &lt;expression&gt; `of` _pattern_ -> _result_

---------------------------------------------------------------

## Lists

Groups of homogeneous objects (same type). Strings are lists of characters.

### Concatentation

| Function 	| Description								| Example
|-----------|-----------------------------------|----------
| ++  		| concats two lists (inefficient) 	| `[1,2] ++ [3,4]` 
| :  			| prepends element to 					| `3 : [4,5]`

### List Functions

| Function 	| Description								| Example
|-----------|-----------------------------------|----------
| !!  		| access to given element of list 	| `[1,2,3] !! 0` 
| <, > == 	| comparison by element 				| `[1,2,3] < [4,5,6]`
| head 		| gets the head element 				| 
| tail 		| gets all elements after first		|
| last 		| gets the last element 				|
| init 		| gets all but last element 			| 
| length 	| get length of list 					| `length [1,2,3]`
| null 		| checks if list is empty 				| `null [1,2,3]`
| reverse 	| reverses a list 						| `reverse [1,2,3]`
| take 		| takes the first **N** elements 	| `take 3 [1,2,3,4,5]`
| drop 		| drops the first **N** elements 	| `drop 2 [1,2,3,4,5]`
| maximum 	| in orderable list, takes largest element | `maximum [1,2,3]`
| minimum 	| in orderable list, takes smallest element | `minimum [1,2,3]`
| sum 		| gets the sum of list of numbers 	| `sum [1,2,3]`
| product 	| gets the product of a list of numbers | `product [1,2,3]`
| elem 		| gets whether a given item is in the given list | `elem 4 [2,3,4]`

### Range operations

| Function 	| Description								| Example
|-----------|-----------------------------------|----------
| .. 			| Ordered range 							| `[1..20] or w/ step [1,5..20] or infinite [1..]`
| cycle 		| duplicates list indefinitely 		| `cycle [1,2]`
| repeat 	| repeats single element as list indefinitely | `repeat 4`
| replicate | repeats element **N** times as list 		| `replicate 4 [1,2]`

### List comprehensions

List comprehensions allow creation of lists using constraints

`[x | x <- [1,6..10], 10 < x && x < 40]`

--------------------------------------------

## Tuples

Fixed size of heterogeneous items (not all must be same type). They are delimited by
parenthesis ().

### Tuple pair functions
| Function 	| Description								| Example
|-----------|-----------------------------------|----------
| fst 		| gets the first in a tuple pair 	| `fst (1,2)`
| snd 		| gets second in a tuple pair 		| `snd (1, "Two")`

### Misc

| Function 	| Description													| Example
|-----------|--------------------------------------------------|----------
| zip 		| combines two lists element-wise into tuple pair 	| `zip [1,2] [4,5]` 

------------------------------------------------------------------------------

## Types

Type annotations are passed using :: 

| Function 	| Description													| Example
|-----------|--------------------------------------------------|----------
| :: 			| type annotation 											| "5" :: String
| compare 	| compares two values of Ord instance 					| `compare 1 2`
| show 		| prints value as a string 								| `show (1,2)`
| read 		| parses a string to a type 								| `read "True" :: Bool`
| minBound 	| finds lower bound of a bounded type 					| minBound :: Int 
| maxBound 	| finds the upper bound of a bounded type 			| maxBound :: Bool
| pred		| finds the previous value									| pred 1
| succ		| finds the next value										| succ 1

--------------------------------------------------------------------------------

## Patterns

Haskell can perform pattern matching like Prolog or Erlang. 

`(x:y:_) = [3,4,5]`

gives `x = 3`, `y = 4`

#### List comprehension pattern matching

`[a + b | (a,b) <- [(1,2),(3,4), (5,6)]]` 

gives

`[3,7,11]`

## As-pattern

To store the name of a pattern, use the form {name}@{pattern}

`pattern@(x:_) = [1,2,3,4]`

gives 

`pattern = [1,2,3,4]` and `x = 1`

------------------------------------------------------------------------------
## Functions
| Function 	| Description													 	| Example
|-----------|-----------------------------------------------------|----------
| $       	| applies a function (right-associative)              | `max $ map (3+) [2,6,1]`  
| .    		| function composition                                | 

## Higher Order Functions

| Function 	| Description													 	| Example
|-----------|-----------------------------------------------------|----------
| zipWith 	| combines two lists element-wise by a given two paramter function | `zipWith (+) [1,2] [3,4]`  
| flip 		| takes a function and return it with the first two arguments flipped | 
| map 		| applies a function to a list 								| `map (+1) [2,3,4,5]`
| filter 	| returns a list that matches the given funciton (predicate) | `filter (>5) [4,5,6]`
| takeWhile | returns a list while the predicate is true 			| `takeWhile (<5) [2,4,6,8]`
| foldl     |                                                     | `foldl (+) 0 [1,2,3]`
| foldl1    |                                                     | `foldl1 (+) [1,2,3]`
| foldr     |                                                     | ``
| foldr1    |                                                     | ``
| scanl     |                                                     | ``
| scanl1    |                                                     | ``
| scanr     |                                                     | ``
| scanr1    |                                                     | ``

-----------------------------------------------------------------------------
## Misc

| Function 	| Description													| Example
|-----------|--------------------------------------------------|----------
| error 		| throws a runtime error										| `error "This is an error"`

## Standard Type Classes
| Type		| Description											
|-----------|---
| Show		| Convertable to string
| Read 		| Convertable from string
| Eq			| Able to be equated
| Num			| Numerical type
| Ord			| Able to be ordered
| Enum		| Has predecessors and successors
| Bounded	| Has lowest and highest value

### Type/Type Classes
A Type is an instance of a Type Class and so it can use the functions defined by the Type Class

### Type Synonyms
A type synonym helps place a context to a type

```
type FirstName = String
type Age = Int
```

### New Types
```
data Gender = Male | Female | Other
```

### Type/Class constraints
a => defines a constraints (e.g. `Eq a => a`)

### Defining
| Keyword			| Description													| Example
|---					|---																|---
| class 				| Defines a Type Class										| `class Eq a where ...`
| instance			| creates a type class which uses (instantiates another type class) | `instance Eq MyType where ...`
| type 				| creates a type synonym									| `type MyType = Eq`
| data 				| create a new data type 									| `data MyType = Nothing | MyType { prop1 :: Int, prop2 :: String } deriving (Show)`

## IO
| Function 			| Description 													| Example
|---					|---																|---
| putStr				| Writes string to stdout									| `putStr "Hi" `
| putStrLn			| Writes string to stdout with new line				| `putStrLn "Hi" `
| getLine			| Gets line from stdin (binds result to variable)	| `variableName <- getLine`
| putChar			| Write a single character to stdout					| `putChar 'a'`
| print				| Write the `show` of a type (putStrLn . show)		| `print True`
| when				| Conditionally perform IO action						| `when [conditional] $ do action`
| sequence			| Performs list of IO actions one after another		| `actions <- sequence [getLine, getLine]`
| mapM/mapM_		| Sequenced mapping (sequence $ map)					| `mapM print [3, 2, 1]`
| forever			| 																	| 

## Strings
| Function 			| Description													| Example
|---					|---																|---
| lines				| Takes a string with newlines and breaks up into array | 
| unlines			| Takes an array of string and returns single string with newlines |


## Files
| Function 			| Description													| Example
|---					|---																|---
| openFile			| 																	| 
| hGetContents		| Gets contents of a handle								|
| hClose				| Closes handle											 	|	
| withFile			|																	|
| readFile			| Read a file													|
| writeFile			| Writes to a file											|
| appendFile		| Appends to a file

## Exceptions
| Function 			| Description													| Example
|---					|---																|---
| bracket			| Cleans up resources										| 
| bracketOnError	| Cleans up on if exception is raised					|

## Command line

**Library:** System.Environment

| Function 			| Description													| Example
|---					|---																|---
| getArgs			| Gets command line arguments								| 
| getProgName		| Gets the application name								|

## Random

**Library:** System.Random

| Function 			| Description																								| Example
|---					|---																											|---
| random				| takes random generator and value to create random number and new random generator	| 
| randoms			|																												|
| randomR			|																												|
| randomRs			|																												|

## Conversions
| Function 			| Description																								| Example
|---					|---																											|---
| fromIntegral		| converts integral number to number																| 
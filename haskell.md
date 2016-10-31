# Haskell Notes (Cheat sheet)

## Numbers 
| Function 	| Description								| Example
|-----------|-----------------------------------|----------
| odd 		| Determines if number is odd 		| `odd 2`  
| even 		| Determines if number is even 		| `even 2` 
| ^ 			| Power of 									| `2^4`

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

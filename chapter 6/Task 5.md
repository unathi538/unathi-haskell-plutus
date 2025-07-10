- HC6T5: Implement a function that reverses a list using recursion.


```haskell
-- Define a recursive function to reverse a list
reverseList :: [a] -> [a]
reverseList [] = []                                -- Base case: empty list
reverseList (x:xs) = reverseList xs ++ [x]         -- Recursive step

-- Main function to run the program
main :: IO ()
main = do
    putStrLn "Enter a list of elements separated by spaces:"
    input <- getLine
    let list = words input                          -- Split input into list of strings
    let result = reverseList list
    putStrLn ("The reversed list is: " ++ unwords result)
```



### Example Output:

```
Enter a list of elements separated by spaces:
one two three
The reversed list is: three two one
```



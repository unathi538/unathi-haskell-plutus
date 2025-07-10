HC6T4: Implement a function to compute the product of elements in a list using foldl.



```haskell
-- Define the sum function using foldr
sumList :: [Int] -> Int
sumList = foldr (+) 0

-- Main function to run the program
main :: IO ()
main = do
    putStrLn "Enter a list of numbers separated by spaces:"
    input <- getLine
    let numbers = map read (words input) :: [Int]
    let result = sumList numbers
    putStrLn ("The sum of the list is " ++ show result)
```



### Example Output:

```
Enter a list of numbers separated by spaces:
1 2 3 4 5
The sum of the list is 15
```


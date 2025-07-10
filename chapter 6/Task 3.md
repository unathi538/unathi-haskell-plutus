- HC6T3: Implement a function to compute the sum of elements in a list using foldr.
- 

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

### How to Run:

1. Save as `SumList.hs`
2. Compile:

   ```bash
   ghc SumList.hs
   ```
3. Run:

   ```bash
   ./SumList
   ```

### Example Output:

```
Enter a list of numbers separated by spaces:
1 2 3 4 5
The sum of the list is 15
```


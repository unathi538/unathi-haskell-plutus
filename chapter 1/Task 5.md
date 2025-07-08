HC1T5 - Task 5: Laziness in Haskell



```haskell
-- Define an infinite list of numbers starting from 1
infiniteNumbers :: [Int]
infiniteNumbers = [1..]

-- Function to get the first n elements from the infinite list
getFirstN :: Int -> [Int]
getFirstN n = take n infiniteNumbers

-- Main function to run the program
main :: IO ()
main = do
    putStrLn "Enter how many numbers you want to take from the infinite list:"
    input <- getLine
    let n = read input :: Int
    let result = getFirstN n
    putStrLn $ "First " ++ show n ++ " numbers: " ++ show result
```

### How it works:

* `infiniteNumbers = [1..]` creates an infinite list of integers starting from 1.
* `take n infiniteNumbers` extracts the first `n` elements from this list.
* `main` prompts the user to enter a number, reads it, and prints the corresponding slice of the infinite list.

### Sample run:

```
Enter how many numbers you want to take from the infinite list:
5
First 5 numbers: [1,2,3,4,5]
```




HC6T2: Implement a recursive function to compute the nth Fibonacci number.


```haskell
-- Define a recursive function to compute the nth Fibonacci number
fibonacci :: Integer -> Integer
fibonacci 0 = 0                          -- Base case 1
fibonacci 1 = 1                          -- Base case 2
fibonacci n = fibonacci (n - 1) + fibonacci (n - 2)  -- Recursive case

-- Main function to run the program
main :: IO ()
main = do
    putStrLn "Enter a number to compute the nth Fibonacci number:"
    input <- getLine
    let n = read input :: Integer
    let result = fibonacci n
    putStrLn ("The " ++ show n ++ "th Fibonacci number is " ++ show result)
```

### How to Run:

1. Save the code as `Fibonacci.hs`.
2. Compile:

   ```bash
   ghc Fibonacci.hs
   ```
3. Run:

   ```bash
   ./Fibonacci
   ```

### Example Output:

```
Enter a number to compute the nth Fibonacci number:
7
The 7th Fibonacci number is 13
```


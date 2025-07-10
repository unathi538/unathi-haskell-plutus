-- HC6T1: Implement a recursive function to compute the factorial of a number.




```haskell
-- Define a recursive factorial function
factorial :: Integer -> Integer
factorial 0 = 1                          -- Base case
factorial n = n * factorial (n - 1)      -- Recursive case

-- Main function to run the program
main :: IO ()
main = do
    putStrLn "Enter a number to compute its factorial:"
    input <- getLine
    let number = read input :: Integer
    let result = factorial number
    putStrLn ("The factorial of " ++ show number ++ " is " ++ show result)
```

### How to run this code:

1. Save the code to a file, e.g., `Factorial.hs`.
2. Compile it with `ghc`:

   ```bash
   ghc Factorial.hs
   ```
3. Run the compiled program:

   ```bash
   ./Factorial
   ```

### Example Output:

```
Enter a number to compute its factorial:
5
The factorial of 5 is 120
```



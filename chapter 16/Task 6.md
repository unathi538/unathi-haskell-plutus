

### Code

```haskell
-- Recursive Fibonacci function
fibonacci :: Integer -> Integer
fibonacci n
  | n < 0     = error "Negative index not allowed"
  | n == 0    = 0
  | n == 1    = 1
  | otherwise = fibonacci (n - 1) + fibonacci (n - 2)

main :: IO ()
main = do
  putStrLn "Enter an integer n to compute the nth Fibonacci number (0-based):"
  input <- getLine
  let maybeNum = reads input :: [(Integer, String)]
  case maybeNum of
    [(n, "")] -> 
      if n < 0 
        then putStrLn "Error: Negative number entered."
        else putStrLn $ "Fibonacci number " ++ show n ++ " is " ++ show (fibonacci n)
    _ -> putStrLn "Invalid input. Please enter a valid non-negative integer."
```

---

### Explanation:

* `fibonacci` is a simple recursive function:

  * Returns 0 for n=0, 1 for n=1.
  * For n > 1, returns sum of the two previous Fibonacci numbers.
  * Throws error for negative n (input is validated in `main`).
* In `main`:

  * Reads user input.
  * Parses input safely using `reads`.
  * Checks that n is non-negative.
  * Computes and prints the nth Fibonacci number.
  * Otherwise, prints an error message.


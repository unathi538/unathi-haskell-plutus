


### Code

```haskell
-- Recursive function to calculate factorial
factorial :: Integer -> Integer
factorial 0 = 1
factorial n
  | n > 0     = n * factorial (n - 1)
  | otherwise = error "Factorial is not defined for negative numbers"

main :: IO ()
main = do
  putStrLn "Enter a non-negative integer to calculate its factorial:"
  input <- getLine
  let maybeNum = reads input :: [(Integer, String)]
  case maybeNum of
    [(n, "")] -> 
      if n < 0 
      then putStrLn "Error: Negative number entered."
      else putStrLn $ "Factorial of " ++ show n ++ " is " ++ show (factorial n)
    _ -> putStrLn "Invalid input. Please enter a valid non-negative integer."
```

---

### Explanation:

* `factorial` is a recursive function:

  * `factorial 0 = 1` is the base case.
  * For positive `n`, it returns `n * factorial (n - 1)`.
  * For negative numbers, it throws an error (though we handle this in `main`).
* In `main`:

  * We prompt the user for input.
  * We use `reads` to safely parse the input string to an `Integer`.
  * If parsing succeeds and the number is non-negative, calculate and print the factorial.
  * Otherwise, print an error message.

---



```haskell
-- DoubleNumber.hs

main :: IO ()
main = do
    putStrLn "Enter a number:"
    input <- getLine
    let number = read input :: Int
    let result = number * 2
    putStrLn ("That number multiplied by 2 is: " ++ show result)
```

### Explanation:

* `getLine` reads user input as a string.
* `read input :: Int` converts the input string to an integer.
* `number * 2` multiplies it.
* `show result` converts the result back to a string for printing.

### How to Run:

1. Save it as `DoubleNumber.hs`.
2. Run it using:

```bash
runhaskell DoubleNumber.hs
```


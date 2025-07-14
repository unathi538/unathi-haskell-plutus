
```haskell
-- Factorial.hs

-- Define the factorial function using recursion
factorial :: Integer -> Integer
factorial 0 = 1
factorial n = n * factorial (n - 1)

-- Main function to run the program
main :: IO ()
main = do
    let number = 5
    let result = factorial number
    putStrLn ("The factorial of " ++ show number ++ " is " ++ show result)
```

### Output:

```
The factorial of 5 is 120
```

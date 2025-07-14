

```haskell
-- Fibonacci.hs

-- Define the recursive Fibonacci function
fibonacci :: Int -> Int
fibonacci 0 = 0
fibonacci 1 = 1
fibonacci n = fibonacci (n - 1) + fibonacci (n - 2)

-- Main function to print the first 10 Fibonacci numbers
main :: IO ()
main = do
    let fibs = [fibonacci n | n <- [0..9]]
    putStrLn "The first 10 Fibonacci numbers are:"
    print fibs
```



### Output:

```
The first 10 Fibonacci numbers are:
[0,1,1,2,3,5,8,13,21,34]
```


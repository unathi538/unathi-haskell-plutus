
```haskell
-- EvenOrOdd.hs

main :: IO ()
main = do
    putStrLn "Enter a number:"
    input <- getLine
    let number = read input :: Int
    if even number
        then putStrLn "That number is even."
        else putStrLn "That number is odd."
```

### Explanation:

* `getLine` reads the user input as a string.
* `read input :: Int` converts the input to an integer.
* `even` is a built-in Haskell function that checks if a number is divisible by 2.
* Based on the result, it prints either "even" or "odd".



```haskell
-- SumTwoNumbers.hs

main :: IO ()
main = do
    putStrLn "Enter the first number:"
    input1 <- getLine
    putStrLn "Enter the second number:"
    input2 <- getLine
    let num1 = read input1 :: Int
    let num2 = read input2 :: Int
    let sumResult = num1 + num2
    putStrLn ("The sum is: " ++ show sumResult)
```

### Explanation:

* `getLine` reads each input as a string.
* `read input1 :: Int` and `read input2 :: Int` convert them to integers.
* `num1 + num2` computes the sum.
* `show` converts the result back to a string for display.


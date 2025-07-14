
```haskell
-- AddTwo.hs

-- Define the function
addTwoNumbers :: Int -> Int -> Int
addTwoNumbers x y = x + y

-- Main function to run the program
main :: IO ()
main = do
    let num1 = 7
    let num2 = 5
    let result = addTwoNumbers num1 num2
    putStrLn ("The sum is: " ++ show result)
```



### Output:

```
The sum is: 12
```


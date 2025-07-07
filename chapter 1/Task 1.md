Task 1: Function Composition



```haskell
-- Define the functions
double :: Int -> Int
double x = x * 2

increment :: Int -> Int
increment x = x + 1

doubleThenIncrement :: Int -> Int
doubleThenIncrement = increment . double  -- function composition

-- Main function to test
main :: IO ()
main = do
    let input = 5
    putStrLn ("Input: " ++ show input)
    putStrLn ("Double: " ++ show (double input))
    putStrLn ("Increment: " ++ show (increment input))
    putStrLn ("Double then Increment: " ++ show (doubleThenIncrement input))
```

### Explanation:

* `double x = x * 2` multiplies input by 2.
* `increment x = x + 1` adds 1 to input.
* `doubleThenIncrement = increment . double` applies `double` first, then passes the result to `increment`.

### Sample Output (for input = 5):

```
Input: 5
Double: 10
Increment: 6
Double then Increment: 11
```



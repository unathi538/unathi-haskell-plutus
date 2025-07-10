HC5T1: Using applyTwice


```haskell
-- Define the function that applies a function three times
applyThreeTimes :: (Int -> Int) -> Int -> Int
applyThreeTimes f x = f (f (f x))

-- Example function to use (e.g., doubling a number)
double :: Int -> Int
double n = n * 2

-- Main function to test applyThreeTimes
main :: IO ()
main = do
    let result = applyThreeTimes double 1
    putStrLn ("Result of applying 'double' three times to 1: " ++ show result)
```

### Explanation:

* `applyThreeTimes` takes a function `f :: Int -> Int` and an integer `x`.
* It applies `f` to `x` three times: `f (f (f x))`.
* The `double` function simply multiplies a number by 2.
* `main` applies `double` three times to `1`, so:

  ```
  double 1 = 2
  double 2 = 4
  double 4 = 8
  ```

**Output when you run it:**

```
Result of applying 'double' three times to 1: 8
```

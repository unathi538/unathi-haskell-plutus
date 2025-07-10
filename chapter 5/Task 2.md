HC5T2: Filtering Odd Numbers


```haskell
-- Use filter to extract odd numbers from 1 to 30
oddNumbers :: [Int]
oddNumbers = filter odd [1..30]

-- Main function to display the result
main :: IO ()
main = do
    putStrLn "Odd numbers from 1 to 30:"
    print oddNumbers
```

### Explanation:

* `[1..30]` generates a list of numbers from 1 to 30.
* `filter odd` keeps only the elements where the `odd` predicate returns `True`.
* `print oddNumbers` outputs the resulting list.

**Expected Output:**

```
Odd numbers from 1 to 30:
[1,3,5,7,9,11,13,15,17,19,21,23,25,27,29]
```

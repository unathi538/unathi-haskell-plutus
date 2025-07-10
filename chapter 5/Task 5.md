HC5T5: Partial Application


```haskell
-- Define multiplyByFive using partial application
multiplyByFive :: Int -> Int
multiplyByFive = (*) 5

-- Main function to test multiplyByFive
main :: IO ()
main = do
    print (multiplyByFive 3)   -- Should print 15
    print (multiplyByFive 10)  -- Should print 50
```

### Explanation:

* `(*) 5` is a partially applied version of the multiplication operator.
* It creates a function that multiplies any given number by 5.
* `multiplyByFive 3` becomes `5 * 3`.

**Expected Output:**

```
15
50
```

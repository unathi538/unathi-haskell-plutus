HC5T4: Using Lambda Functions


```haskell
-- Rewrite using a lambda function
biggerThan10 :: Int -> Bool
biggerThan10 = \x -> x > 10

-- Main function to test it
main :: IO ()
main = do
    print (biggerThan10 5)   -- Should print False
    print (biggerThan10 15)  -- Should print True
```

### Explanation:

* `\x -> x > 10` is a **lambda function** (anonymous function) equivalent to `biggerThan10 x = x > 10`.
* The type `Int -> Bool` means it takes an `Int` and returns a `Bool`.

**Expected Output:**

```
False
True
```



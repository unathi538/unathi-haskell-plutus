Here's a complete and working Haskell example that defines a function `compareValues` which returns the larger of two values, assuming the type `a` is both an instance of `Eq` and `Ord`. The `main` function demonstrates its usage with integers and characters.

```haskell
-- compareValues.hs

-- Function that returns the larger of two values
compareValues :: (Eq a, Ord a) => a -> a -> a
compareValues x y
  | x >= y    = x
  | otherwise = y

-- Main function to test compareValues
main :: IO ()
main = do
  -- Comparing integers
  let intResult = compareValues 42 27
  putStrLn $ "Larger integer: " ++ show intResult

  -- Comparing characters
  let charResult = compareValues 'a' 'z'
  putStrLn $ "Larger character: " ++ show charResult
```

### Explanation:

* `compareValues` takes two values `x` and `y`.
* The type constraint `(Eq a, Ord a)` ensures that the type supports both equality and ordering.
* It uses a guard to compare the values and returns the larger one.
* The `main` function demonstrates the function with both `Int` and `Char` types.

### How to run:

Save the code to a file named `compareValues.hs` and run it using GHC:

```bash
ghc compareValues.hs -o compareValues
./compareValues
```

**Expected Output:**

```
Larger integer: 42
Larger character: z
```





### ✅ Haskell Code Example

```haskell
-- Function to compare two values and return the larger one
compareValues :: (Eq a, Ord a) => a -> a -> a
compareValues x y
    | x >= y    = x
    | otherwise = y

-- Main function to test compareValues
main :: IO ()
main = do
    let a = 42
    let b = 27
    let c = "apple"
    let d = "banana"

    putStrLn $ "Larger of " ++ show a ++ " and " ++ show b ++ ": " ++ show (compareValues a b)
    putStrLn $ "Larger of \"" ++ c ++ "\" and \"" ++ d ++ "\": " ++ show (compareValues c d)
```

---

### 🧠 Explanation:

* `compareValues` uses a type constraint: `(Eq a, Ord a) =>` which means `a` must support equality and ordering.
* Uses guards to return the greater value using the `>=` operator.
* Demonstrates usage with both `Int` and `String` types.

---

### 💡 Sample Output:

```
Larger of 42 and 27: 42
Larger of "apple" and "banana": "banana"
```


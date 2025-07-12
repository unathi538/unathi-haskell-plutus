

* Defines a type class `MinMax` with methods `minValue :: a` and `maxValue :: a`,
* Provides an instance of `MinMax` for `Int`,
* Includes a `main` function to demonstrate the use of the class.

---

### ✅ Full Working Example

```haskell
-- Define the MinMax type class
class MinMax a where
  minValue :: a
  maxValue :: a

-- Implement MinMax for Int
instance MinMax Int where
  minValue = minBound
  maxValue = maxBound

-- Main function to demonstrate
main :: IO ()
main = do
  putStrLn "Min and Max for Int:"
  putStrLn $ "Minimum Int: " ++ show (minValue :: Int)
  putStrLn $ "Maximum Int: " ++ show (maxValue :: Int)
```

---

### 🔍 Explanation

* The `MinMax` type class defines two methods: `minValue` and `maxValue`.
* For the `Int` instance, it uses the built-in `minBound` and `maxBound` (since `Int` is already an instance of `Bounded`).
* In `main`, we explicitly specify the type `Int` to guide type inference.

---

### 💡 Sample Output

```
Min and Max for Int:
Minimum Int: -9223372036854775808
Maximum Int: 9223372036854775807
```

> Note: Output may vary slightly depending on your system's `Int` size (e.g., 32-bit vs 64-bit).


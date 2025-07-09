HC2T6 - Task 6: Understanding Int vs Integer



1. Defines an `Int` variable `smallNumber` with the value `2^62`.
2. Defines an `Integer` variable `bigNumber` with the value `2^127`.
3. Includes a demonstration of evaluating `2^64 :: Int` to show what happens when the value exceeds the range of `Int`.

> 💡 In Haskell, `Int` is a fixed-size integer (typically 64-bit), while `Integer` can represent arbitrarily large numbers.

---

### ✅ Haskell Code (With GHCi-Safe Output)

```haskell
-- Define smallNumber using Int
smallNumber :: Int
smallNumber = 2^62
-- This is within the 64-bit signed Int range

-- Define bigNumber using Integer
bigNumber :: Integer
bigNumber = 2^127
-- Integer supports arbitrary-precision arithmetic

-- Try evaluating 2^64 as Int
overflowExample :: Int
overflowExample = 2^64
-- This will compile, but overflow at runtime because 2^64 > maxBound :: Int

main :: IO ()
main = do
    putStrLn "Values within and beyond Int range:"
    
    putStrLn $ "2^62 as Int (smallNumber): " ++ show smallNumber
    putStrLn $ "2^127 as Integer (bigNumber): " ++ show bigNumber

    putStrLn "\nEvaluating 2^64 :: Int (will overflow):"
    putStrLn $ "2^64 as Int (overflowExample): " ++ show overflowExample
```

---

### 🧪 Sample Output

Depending on your system (64-bit), here's what you will typically see:

```
Values within and beyond Int range:
2^62 as Int (smallNumber): 4611686018427387904
2^127 as Integer (bigNumber): 170141183460469231731687303715884105728

Evaluating 2^64 :: Int (will overflow):
2^64 as Int (overflowExample): 0
```

> ⚠️ **Explanation**:

* `2^64 :: Int` **overflows** on a 64-bit system because `Int` only supports up to `2^63 - 1`. The result wraps around (likely to `0`, but exact behavior can vary).
* Use `Integer` for large values to avoid overflow.

---

### ✅ Recommendation

To avoid overflow, **use `Integer`** when working with large numbers:

```haskell
safeBig = 2^100 :: Integer
```



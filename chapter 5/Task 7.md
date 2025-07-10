HC5T7: The $ Operator



### ✅ **Original Function:**

```haskell
result = sum (map (*2) (filter (>3) [1..10]))
```

---

### ✅ **Rewritten Using `$` Operator:**

```haskell
result :: Int
result = sum $ map (*2) $ filter (>3) [1..10]

-- Main function to run and display the result
main :: IO ()
main = do
    putStrLn "Result using $ operator:"
    print result
```

---

### 💡 **Explanation:**

* The `$` operator allows you to eliminate parentheses.
* It's right-associative, so:

  ```haskell
  sum $ map (*2) $ filter (>3) [1..10]
  ```

  is equivalent to:

  ```haskell
  sum (map (*2) (filter (>3) [1..10]))
  ```

---

### ✅ **Expected Output:**

```
Result using $ operator:
84
```


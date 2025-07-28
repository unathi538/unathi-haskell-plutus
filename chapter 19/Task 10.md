
 

### ✅ **HC19T10: `combineResults` using `Either` applicative**

```haskell
combineResults :: Either String Int -> Either String Int -> Either String Int
combineResults = liftA2 (+)

main :: IO ()
main = do
  print $ combineResults (Right 5) (Right 7)     -- Right 12
  print $ combineResults (Left "Error1") (Right 7) -- Left "Error1"
  print $ combineResults (Right 5) (Left "Error2") -- Left "Error2"
```

**Explanation:**

* `liftA2 (+)` adds two `Either` values, short-circuiting on the first `Left`.

---

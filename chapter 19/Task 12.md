

### ✅ **HC11T2: `sumThreeApplicative` with `Either`**

```haskell
sumThreeApplicative :: Either String Int -> Either String Int -> Either String Int -> Either String Int
sumThreeApplicative a b c = (\x y z -> x + y + z) <$> a <*> b <*> c

main :: IO ()
main = do
  print $ sumThreeApplicative (Right 1) (Right 2) (Right 3)   -- Right 6
  print $ sumThreeApplicative (Left "A") (Right 2) (Right 3)  -- Left "A"
  print $ sumThreeApplicative (Right 1) (Left "B") (Right 3)  -- Left "B"
```

**Explanation:**

* The lambda combines three `Right` values or short-circuits at the first `Left`.

---


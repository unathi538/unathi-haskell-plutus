
### ✅ **HC19T9: `pureAndApply` with `pure`**

```haskell
pureAndApply :: IO Int
pureAndApply = pure (+3) <*> pure 7

main :: IO ()
main = do
  result <- pureAndApply
  putStrLn $ "pure (+3) <*> pure 7 = " ++ show result
```

**Explanation:**

* `pure (+3)` lifts a function into an applicative context.
* `<*>` applies it to another applicative (`pure 7`).

---


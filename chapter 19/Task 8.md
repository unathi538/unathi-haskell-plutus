

### ✅ **HC19T8: `discardSecond` using `<*`**

```haskell
discardSecond :: IO a -> IO b -> IO a
discardSecond = (<*)

main :: IO ()
main = do
  result <- discardSecond (putStrLn "First effect" >> return 1)
                           (putStrLn "Second effect" >> return 2)
  putStrLn $ "Result: " ++ show result
```

**Explanation:**

* `<*` runs both effects, returns the result of the first.
* `>> return 1` ensures we get an `IO Int` and not just `IO ()`.

---


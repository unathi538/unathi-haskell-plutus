
Here’s a complete example including the function `applyToMaybe` and a `main` to demonstrate:

```haskell
-- Function that applies a function to the value inside a Maybe using fmap
applyToMaybe :: (a -> b) -> Maybe a -> Maybe b
applyToMaybe = fmap

main :: IO ()
main = do
  let maybeVal1 = Just 10
  let maybeVal2 = Nothing

  putStrLn "Original Maybe values:"
  print maybeVal1
  print maybeVal2

  let result1 = applyToMaybe (*2) maybeVal1
  let result2 = applyToMaybe (*2) maybeVal2

  putStrLn "\nAfter applying (*2) using applyToMaybe:"
  print result1
  print result2
```

---

### Explanation:

* `applyToMaybe` is just `fmap` specialized to `Maybe`.
* Applying `(*2)` doubles the value inside `Just`.
* For `Nothing`, the function does nothing and returns `Nothing`.
* The `main` function prints the before and after states.

---


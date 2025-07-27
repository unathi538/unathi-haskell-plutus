

### ✅ Full Working Example:

```haskell
-- Function to add three Maybe Int values using applicative style
addThreeApplicative :: Maybe Int -> Maybe Int -> Maybe Int -> Maybe Int
addThreeApplicative mx my mz = (\x y z -> x + y + z) <$> mx <*> my <*> mz

main :: IO ()
main = do
  let a = Just 10
  let b = Just 20
  let c = Just 30
  let d = Nothing

  putStrLn "Adding three Just values:"
  print $ addThreeApplicative a b c  -- Just 60

  putStrLn "\nAdding with a Nothing value:"
  print $ addThreeApplicative a b d  -- Nothing
```

---

### 📘 Explanation:

* `(<$>)` is infix for `fmap`, and `<*>` is infix for `ap` (function application within a context).
* `(\x y z -> x + y + z)` is a function taking 3 arguments.
* `Just` wraps a value; if any of the inputs is `Nothing`, the result is `Nothing`.
* This works because `Maybe` is an instance of `Applicative`.

---


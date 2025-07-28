
### ✅ Goal:

Define:

```haskell
liftAndMultiply :: Applicative f => f Int -> f Int -> f Int
```

This lifts `(*)` into a context like `Maybe Int`, `Either String Int`, or even `IO Int`.

---

### ✅ Full Working Example with `Maybe`:

```haskell
import Control.Applicative (liftA2)

-- Lift multiplication into any Applicative (e.g., Maybe, Either, etc.)
liftAndMultiply :: Applicative f => f Int -> f Int -> f Int
liftAndMultiply = liftA2 (*)

main :: IO ()
main = do
  let a = Just 6
  let b = Just 7
  let c = Nothing

  putStrLn "Using liftAndMultiply with Maybe:"
  print $ liftAndMultiply a b  -- Just 42
  print $ liftAndMultiply a c  -- Nothing
```

---

### 🧠 Explanation:

* `liftA2 (*)` turns `(*) :: Int -> Int -> Int` into a function that works in any `Applicative`, like `Maybe`.
* `liftAndMultiply (Just 6) (Just 7)` results in `Just (6 * 7) = Just 42`.
* If either value is `Nothing`, the result is `Nothing`.

---




## ✅ Full Working Code

```haskell
import Data.Semigroup (Semigroup(..))
import Data.Monoid (Sum(..), getSum)

-- Fold a list using the Semigroup operation
foldWithSemigroup :: Semigroup a => [a] -> a
foldWithSemigroup = foldr1 (<>)

main :: IO ()
main = do
  let sums = [Sum 1, Sum 2, Sum 3, Sum 4]  -- Sum is a Monoid/Semigroup wrapper for addition
  putStrLn "Folding a list of Sum Int using foldWithSemigroup:"
  let foldedSum = foldWithSemigroup sums
  putStrLn $ "Result: " ++ show (getSum foldedSum)

  let strings = ["Hello, ", "world", "!"]
  putStrLn "\nFolding a list of Strings using foldWithSemigroup:"
  let foldedString = foldWithSemigroup strings
  putStrLn $ "Result: " ++ foldedString
```

---

## 🔍 Explanation

* `foldWithSemigroup`:

  * Uses `foldr1` and the Semigroup operator `(<>)` to combine all elements.
  * **Note:** `foldr1` requires the list to be non-empty; it will crash on an empty list.

* In `main`:

  * We demonstrate folding a list of `Sum Int` values, which sum the integers.
  * We also fold a list of `String`s, which concatenates them (since `String` is a list of `Char` and has a Semigroup instance).

---

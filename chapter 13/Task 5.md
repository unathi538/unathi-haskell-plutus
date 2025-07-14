
Here’s the refactored `SumNonEmpty` module where the helper error message is defined internally but **not exported**:

```haskell
-- File: SumNonEmpty.hs
module SumNonEmpty (sumNonEmpty) where

-- Internal helper for error message (not exported)
emptyListError :: a
emptyListError = error "sumNonEmpty: empty list"

-- Public function exported by the module
sumNonEmpty :: Num a => [a] -> a
sumNonEmpty [] = emptyListError
sumNonEmpty xs = sum xs
```

And the same `Main.hs` for testing:

```haskell
import SumNonEmpty (sumNonEmpty)

main :: IO ()
main = do
    putStrLn "Sum of [1, 2, 3]:"
    print $ sumNonEmpty [1, 2, 3]

    putStrLn "Sum of [] (this will cause an error):"
    print $ sumNonEmpty []
```

---

### Explanation:

* In the module export list `(sumNonEmpty)`, only `sumNonEmpty` is exported.
* The helper `emptyListError` is defined but **not exported**, so it’s private to the module.
* This encapsulates the error logic inside the module.
* The public API is clean and only exposes what’s necessary.

---


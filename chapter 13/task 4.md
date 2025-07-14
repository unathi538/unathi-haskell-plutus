Sure! Below is a Haskell module named `SumNonEmpty` that defines a function `sumNonEmpty`. This function sums a list of numbers but throws an error if the list is empty.

I also include a `main` function to demonstrate how to use it.

```haskell
-- File: SumNonEmpty.hs
module SumNonEmpty (sumNonEmpty) where

-- | sumNonEmpty sums a list of numbers, but throws an error if the list is empty.
sumNonEmpty :: Num a => [a] -> a
sumNonEmpty [] = error "sumNonEmpty: empty list"
sumNonEmpty xs = sum xs
```

And here is a separate `Main.hs` file to test it:

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

* The `SumNonEmpty` module exports the `sumNonEmpty` function.
* `sumNonEmpty` pattern matches on the list:

  * If the list is empty, it throws an error with a descriptive message.
  * Otherwise, it uses the built-in `sum` function to sum the elements.
* The `main` function calls `sumNonEmpty` twice:

  * Once with a non-empty list `[1, 2, 3]`, which prints the sum `6`.
  * Once with an empty list `[]`, which causes a runtime error.

---


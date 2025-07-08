HC1T8 - Task 8: Higher-Order Functions



```haskell
-- Define the applyTwice function
applyTwice :: (a -> a) -> a -> a
applyTwice f x = f (f x)

-- Example usage in main
main :: IO ()
main = do
    -- Using applyTwice with (+1)
    let result1 = applyTwice (+1) 5      -- (5 + 1) + 1 = 7
    putStrLn ("applyTwice (+1) 5 = " ++ show result1)

    -- Using applyTwice with (*2)
    let result2 = applyTwice (*2) 3      -- (3 * 2) * 2 = 12
    putStrLn ("applyTwice (*2) 3 = " ++ show result2)

    -- Using applyTwice with reverse
    let result3 = applyTwice reverse "hello"  -- reverse (reverse "hello") = "hello"
    putStrLn ("applyTwice reverse \"hello\" = " ++ show result3)
```

### Explanation:

* `applyTwice f x = f (f x)` means: apply `f` to `x`, then apply `f` again to the result.
* In `main`, we demonstrate this with:

  * Numbers using `(+1)` and `(*2)`.
  * A string using `reverse` (which reverses back to the original when done twice).

### To Run:

1. Save the code in a file, e.g., `ApplyTwice.hs`
2. Compile or run with GHC or GHCi:

   ```bash
   ghc ApplyTwice.hs -o applytwice && ./applytwice
   ```

   Or in GHCi:

   ```bash
   ghci ApplyTwice.hs
   *Main> main
   ```

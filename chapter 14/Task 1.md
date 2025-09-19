


## Step 2: Edit `app/Main.hs`

Replace contents of `app/Main.hs` with:

```haskell
module Main where

-- | Main entry point of the program
main :: IO ()
main = putStrLn "Hello, Cabal!"
```

Explanation:

* `main :: IO ()` is the main function that runs when you execute the program.
* `putStrLn` prints a string followed by a newline.

---


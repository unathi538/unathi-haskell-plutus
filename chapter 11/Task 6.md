
```haskell
-- UppercaseInput.hs

import Data.Char (toUpper)

main :: IO ()
main = do
    putStrLn "Enter a line of text:"
    line <- getLine
    let upperLine = map toUpper line
    putStrLn ("Uppercase version: " ++ upperLine)
```

### Explanation:

* `getLine` reads a line from the user.
* `map toUpper line` applies the `toUpper` function to each character in the string.
* `toUpper` comes from the `Data.Char` module, so we import it at the top.
* `putStrLn` prints the result.

### How to Run:

1. Save it as `UppercaseInput.hs`.
2. Run it with:

```bash
runhaskell UppercaseInput.hs
```


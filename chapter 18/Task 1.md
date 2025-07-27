

## ✅ Code

```haskell
import Data.Char (toLower)

-- Use fmap to convert all characters in a string to lowercase
mapToLower :: String -> String
mapToLower = fmap toLower

main :: IO ()
main = do
  putStrLn "Enter a string to convert to lowercase:"
  input <- getLine
  let lowerStr = mapToLower input
  putStrLn $ "Lowercase string: " ++ lowerStr
```

---

## 🔍 Explanation

* `fmap` applies a function over a Functor. Lists are Functors, so `fmap toLower` applies `toLower` to each character.
* `toLower` from `Data.Char` converts a single character to lowercase.
* In `main`, we read input, apply `mapToLower`, and print the result.

---


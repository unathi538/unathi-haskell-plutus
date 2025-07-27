

### Code

```haskell
import Data.Char (toUpper)

-- Function to convert a string to uppercase
toUpperCase :: String -> String
toUpperCase = map toUpper

main :: IO ()
main = do
  putStrLn "Enter a string to convert to uppercase:"
  input <- getLine
  let upperStr = toUpperCase input
  putStrLn $ "Uppercase string: " ++ upperStr
```

---

### Explanation:

* We import `toUpper` from `Data.Char` to convert characters to uppercase.
* `toUpperCase` applies `toUpper` to each character in the input string using `map`.
* In `main`, we read a string from the user, convert it using `toUpperCase`, and print the result.

---


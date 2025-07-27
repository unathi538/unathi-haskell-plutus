

### Code

```haskell
-- Function to reverse a string
reverseString :: String -> String
reverseString = reverse

main :: IO ()
main = do
  putStrLn "Enter a string to reverse:"
  input <- getLine
  let reversed = reverseString input
  putStrLn $ "Reversed string: " ++ reversed
```

---

### Explanation:

* `reverseString` is a function that takes a `String` and returns the reversed version using Haskell’s built-in `reverse` function.
* `main` prompts the user to enter a string.
* It reads the input with `getLine`.
* It applies `reverseString` to the input.
* It prints the reversed string.


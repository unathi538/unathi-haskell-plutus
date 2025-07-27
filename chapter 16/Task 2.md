

### Code

```haskell
-- Function to check if a string is a palindrome
isPalindrome :: String -> Bool
isPalindrome s = cleaned == reverse cleaned
  where
    -- Optional: clean string by removing spaces and making lowercase for case-insensitive check
    cleaned = map toLower (filter (/= ' ') s)

import Data.Char (toLower)

main :: IO ()
main = do
  putStrLn "Enter a string to check if it's a palindrome:"
  input <- getLine
  if isPalindrome input
    then putStrLn "Yes, it is a palindrome!"
    else putStrLn "No, it is not a palindrome."
```

---

### Explanation:

* `isPalindrome` compares the cleaned input string with its reverse.
* `cleaned` removes spaces and converts letters to lowercase, so the check is case-insensitive and ignores spaces.
* `main` reads user input and prints whether the input is a palindrome.

---


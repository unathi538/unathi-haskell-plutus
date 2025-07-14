
```haskell
-- Palindrome.hs

import Data.Char (toLower, isAlphaNum)

-- Function to check if a string is a palindrome
isPalindrome :: String -> Bool
isPalindrome str = cleanStr == reverse cleanStr
  where cleanStr = map toLower (filter isAlphaNum str)

-- Main function to get input from the user and check for palindrome
main :: IO ()
main = do
    putStrLn "Enter a string to check if it's a palindrome:"
    input <- getLine
    if isPalindrome input
        then putStrLn "It is a palindrome!"
        else putStrLn "It is not a palindrome."
```

hs
```

### Example Usage:

**Input:**

```
Enter a string to check if it's a palindrome:
Madam
```

**Output:**

```
It is a palindrome!
```


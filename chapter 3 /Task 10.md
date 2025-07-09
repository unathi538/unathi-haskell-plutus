HC3T10 - Advanced Task 10: Check if a string is a palindrome using recursion and guards



### ✅ Haskell Code with Explanation

```haskell
-- Function to check if a string is a palindrome using guards
isPalindrome :: String -> Bool
isPalindrome str
    | length str <= 1 = True  -- A string with 0 or 1 characters is always a palindrome
    | head str == last str = isPalindrome (init (tail str))  -- Check the inner substring recursively
    | otherwise = False  -- If first and last characters don't match, it's not a palindrome

-- Main function to test isPalindrome
main :: IO ()
main = do
    putStrLn ("isPalindrome \"racecar\" = " ++ show (isPalindrome "racecar"))  -- True
    putStrLn ("isPalindrome \"haskell\" = " ++ show (isPalindrome "haskell"))  -- False
    putStrLn ("isPalindrome \"madam\" = " ++ show (isPalindrome "madam"))      -- True
```

---

### 🧠 Explanation

* **Function signature**:

  ```haskell
  isPalindrome :: String -> Bool
  ```

  It takes a `String` and returns a `Bool` indicating whether the string is a palindrome.

* **Guards**:

  * `length str <= 1`: Base case — any empty string or single-character string is a palindrome.
  * `head str == last str`: If the first and last characters match, recursively check the middle part.

    * `tail str`: removes the first character.
    * `init str`: removes the last character.
  * `otherwise`: If first and last characters don’t match, return `False`.

---


### 🖨️ Sample Output

```
isPalindrome "racecar" = True
isPalindrome "haskell" = False
isPalindrome "madam" = True
```


HC5T3: Checking for Uppercase Letters


```haskell
import Data.Char (isUpper)

-- Function to check if a word starts with an uppercase letter
startsWithUpper :: String -> Bool
startsWithUpper []     = False
startsWithUpper (x:_)  = isUpper x

-- Function to check if any word in the list starts with an uppercase letter
anyStartsWithUpper :: [String] -> Bool
anyStartsWithUpper words = any startsWithUpper words

-- Main function to test it
main :: IO ()
main = do
    let wordsList1 = ["hello", "world", "Example"]
    let wordsList2 = ["this", "is", "all", "lowercase"]
    
    putStrLn $ "Does wordsList1 contain any word starting with uppercase? " ++ show (anyStartsWithUpper wordsList1)
    putStrLn $ "Does wordsList2 contain any word starting with uppercase? " ++ show (anyStartsWithUpper wordsList2)
```

### Explanation:

* `startsWithUpper` checks if the first character of a word is uppercase using `isUpper`.
* `any startsWithUpper words` returns `True` if **any word** in the list meets that condition.
* The `main` function tests two lists and prints the results.

**Expected Output:**

```
Does wordsList1 contain any word starting with uppercase? True
Does wordsList2 contain any word starting with uppercase? False
```

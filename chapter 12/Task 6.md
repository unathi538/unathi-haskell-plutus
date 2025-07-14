

```haskell
-- SortList.hs

import Data.List (sort)
import Data.Char (isSpace)

-- Helper function to split input string into integers
readIntList :: String -> [Int]
readIntList input = map read (words input)

-- Main function
main :: IO ()
main = do
    putStrLn "Enter a list of integers separated by spaces:"
    input <- getLine
    let numbers = readIntList input
    let sortedNumbers = sort numbers
    putStrLn "The sorted list is:"
    print sortedNumbers
```

---

### ✅ How to Run:

1. Save as `SortList.hs`.
2. In terminal:

```bash
runghc SortList.hs
```

---

### 💡 Example:

**Input:**

```
Enter a list of integers separated by spaces:
5 2 9 1 3
```

**Output:**

```
The sorted list is:
[1,2,3,5,9]
```






### ✅ **Working Code: Safe Input Parsing with `readMaybe`**

```haskell
-- SafeInputParsing.hs
module Main where

import Text.Read (readMaybe)

-- Function to safely parse input and add two numbers
addNumbers :: String -> String -> Maybe Double
addNumbers xStr yStr = do
    x <- readMaybe xStr :: Maybe Double
    y <- readMaybe yStr :: Maybe Double
    return (x + y)

-- Main function
main :: IO ()
main = do
    putStrLn "Enter the first number:"
    input1 <- getLine
    putStrLn "Enter the second number:"
    input2 <- getLine

    case addNumbers input1 input2 of
        Just result -> putStrLn $ "The sum is: " ++ show result
        Nothing     -> putStrLn "Error: One or both inputs were not valid numbers."
```

---


### 🧠 Example Output

**Valid input:**

```
Enter the first number:
12.5
Enter the second number:
7.3
The sum is: 19.8
```

**Invalid input:**

```
Enter the first number:
abc
Enter the second number:
10
Error: One or both inputs were not valid numbers.
```

---

### 📘 Explanation

* `readMaybe` returns `Nothing` on parse failure instead of crashing, making it safer than `read`.
* The `addNumbers` function uses the `Maybe` monad (`do` block) to sequence the parsing.
* If either input is invalid, the entire operation returns `Nothing`.


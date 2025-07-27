

### ✅ **Code Example: Safe Division Using `Either`**

```haskell
-- EitherDivision.hs
module Main where

import Text.Read (readMaybe)

-- Define a division function that returns Either String Double
safeDivide :: Double -> Double -> Either String Double
safeDivide _ 0 = Left "Error: Cannot divide by zero."
safeDivide x y = Right (x / y)

-- Parse input and perform division, with detailed error messages
divideWithInput :: String -> String -> Either String Double
divideWithInput xStr yStr = do
    x <- case readMaybe xStr :: Maybe Double of
            Just n  -> Right n
            Nothing -> Left "Error: Invalid input for numerator."
    y <- case readMaybe yStr :: Maybe Double of
            Just n  -> Right n
            Nothing -> Left "Error: Invalid input for denominator."
    safeDivide x y

-- Main function
main :: IO ()
main = do
    putStrLn "Enter numerator:"
    numStr <- getLine
    putStrLn "Enter denominator:"
    denomStr <- getLine

    case divideWithInput numStr denomStr of
        Right result -> putStrLn $ "Result: " ++ show result
        Left errMsg  -> putStrLn errMsg
```

---



### 🧠 Example Outputs

**Valid Input:**

```
Enter numerator:
100
Enter denominator:
25
Result: 4.0
```




### 📘 Explanation

* `Either String Double` allows us to return a **meaningful error** (`Left "..."`) or a **result** (`Right value`).
* `readMaybe` is used to parse strings safely.
* `case` expressions help convert `Maybe` to `Either`, making error handling more descriptive.



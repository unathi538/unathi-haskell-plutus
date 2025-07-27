

### ✅ **Code Example: Safe Division using `Maybe`**

```haskell
-- SafeDivision.hs
module Main where

import Text.Read (readMaybe)

-- Safe division function using Maybe
safeDivide :: Double -> Double -> Maybe Double
safeDivide _ 0 = Nothing
safeDivide x y = Just (x / y)

-- Helper to display the result of Maybe Double
showResult :: Maybe Double -> String
showResult Nothing  = "Error: Division by zero is not allowed."
showResult (Just r) = "Result: " ++ show r

-- Main function
main :: IO ()
main = do
    putStrLn "Enter the numerator:"
    numStr <- getLine
    putStrLn "Enter the denominator:"
    denomStr <- getLine

    let maybeNum   = readMaybe numStr :: Maybe Double
        maybeDenom = readMaybe denomStr :: Maybe Double

    case (maybeNum, maybeDenom) of
        (Just num, Just denom) -> putStrLn $ showResult (safeDivide num denom)
        _ -> putStrLn "Error: Invalid input. Please enter valid numbers."
```

---



### 🧠 Example Output

**Valid input:**

```
Enter the numerator:
10
Enter the denominator:
2
Result: 5.0
```

**Divide by zero:**

```
Enter the numerator:
10
Enter the denominator:
0
Error: Division by zero is not allowed.
```

**Invalid input:**

```
Enter the numerator:
ten
Enter the denominator:
2
Error: Invalid input. Please enter valid numbers.
```

---

### 📘 Explanation

* `safeDivide` uses pattern matching:

  * Returns `Nothing` if the denominator is zero.
  * Returns `Just result` otherwise.
* `readMaybe` safely parses strings into `Double`, avoiding crashes on invalid input.
* `Maybe` helps us avoid exceptions by explicitly handling the divide-by-zero case.


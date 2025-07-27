

* Calculates **velocity = distance / time**.
* Uses `readMaybe` to **safely parse** user input.
* Uses `Maybe` to **handle divide-by-zero and invalid input errors** cleanly.

---

### ✅ **Working Example: Velocity Calculator with Error Handling**

```haskell
-- VelocityCalculator.hs
module Main where

import Text.Read (readMaybe)

-- Safe division function using Maybe
safeDivide :: Double -> Double -> Maybe Double
safeDivide _ 0 = Nothing
safeDivide d t = Just (d / t)

-- Calculates velocity if both inputs are valid
calculateVelocity :: String -> String -> Maybe Double
calculateVelocity distStr timeStr = do
    dist <- readMaybe distStr :: Maybe Double
    time <- readMaybe timeStr :: Maybe Double
    safeDivide dist time

-- Main function
main :: IO ()
main = do
    putStrLn "Enter distance (meters):"
    distInput <- getLine
    putStrLn "Enter time (seconds):"
    timeInput <- getLine

    case calculateVelocity distInput timeInput of
        Just v  -> putStrLn $ "Velocity is: " ++ show v ++ " m/s"
        Nothing -> putStrLn "Error: Invalid input or division by zero."
```

---


### 🧠 Example Output

**Valid input:**

```
Enter distance (meters):
100
Enter time (seconds):
10
Velocity is: 10.0 m/s
```

**Invalid input (e.g. text):**

```
Enter distance (meters):
abc
Enter time (seconds):
10
Error: Invalid input or division by zero.
```

**Divide by zero:**

```
Enter distance (meters):
100
Enter time (seconds):
0
Error: Invalid input or division by zero.
```

---

### 📘 Explanation

* `readMaybe` safely parses input strings into `Double`, returning `Nothing` on failure.
* `safeDivide` protects against divide-by-zero errors.
* The `calculateVelocity` function chains parsing and division using the `Maybe` monad to avoid nested conditionals.



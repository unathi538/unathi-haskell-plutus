Perfect — let’s build a **Haskell program that safely reads input from a file, handles exceptions, and computes velocity**.

We’ll:

1. Read a file containing distance and time.
2. Parse the values.
3. Compute velocity = distance / time.
4. Handle exceptions like missing file, bad input, or division by zero.

---

## Full Working Example

```haskell
{-# LANGUAGE ScopedTypeVariables #-}

import System.IO
import Control.Exception
import Text.Read (readMaybe)

-- | Compute velocity given distance and time.
velocity :: Double -> Double -> Either String Double
velocity d t
  | t == 0    = Left "Error: Time cannot be zero (division by zero)."
  | otherwise = Right (d / t)

-- | Safely read numbers from a file
-- File format: two numbers separated by whitespace
-- Example:
-- 100
-- 20
readDistanceTime :: FilePath -> IO (Either String (Double, Double))
readDistanceTime path = do
  result <- try (readFile path) :: IO (Either IOException String)
  case result of
    Left ex  -> return $ Left $ "File error: " ++ show ex
    Right content ->
      case mapM readMaybe (words content) of
        Just [d, t] -> return $ Right (d, t)
        _           -> return $ Left "Parse error: File must contain two numbers."

-- | Main program
main :: IO ()
main = do
  putStrLn "Enter the filename containing distance and time:"
  fileName <- getLine
  values <- readDistanceTime fileName
  case values of
    Left err -> putStrLn err
    Right (d, t) ->
      case velocity d t of
        Left err      -> putStrLn err
        Right vel     -> putStrLn $ "Velocity = " ++ show vel ++ " units/time"
```

---



## Running

```bash
ghc Velocity.hs -o velocity
./velocity
```


Output:

```
Velocity = 5.0 units/time
```

---

## ✅ Explanation

1. **`try`** from `Control.Exception` safely wraps `readFile`, catching IO errors (like file not found).
2. **`readMaybe`** ensures parsing fails gracefully if file content is not valid numbers.
3. The `velocity` function prevents division by zero by returning a `Left` error message.
4. We use **pattern matching** in `main` to handle success or failure at every step.

---

Would you like me to extend this so the program **also falls back to asking the user for manual input** if the file read fails? That way it always has a recovery path.


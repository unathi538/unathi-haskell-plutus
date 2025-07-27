

* Use `Either` to handle errors like division by zero or invalid input parsing.
* Use `IO` exceptions to handle errors from user input (e.g., reading from the console).

**Key points:**

* The program prompts the user to enter distance and time.
* It attempts to parse the inputs into `Double` values.
* If parsing fails, it returns an `Either` error.
* It checks for zero time to avoid division by zero.
* Any unexpected IO exceptions while reading input are caught and handled gracefully.

---

### Code with explanation

```haskell
import Control.Exception (try, IOException)
import Text.Read (readMaybe)

-- Calculate velocity with Either error handling
velocity :: Double -> Double -> Either String Double
velocity distance time
  | time == 0 = Left "Error: Time cannot be zero (division by zero)."
  | otherwise = Right (distance / time)

-- Parse a Double from String with error
parseDouble :: String -> Either String Double
parseDouble s =
  case readMaybe s of
    Just d  -> Right d
    Nothing -> Left $ "Error: Could not parse '" ++ s ++ "' as a number."

-- Safely read a line from stdin, catching IO exceptions
safeGetLine :: IO (Either IOException String)
safeGetLine = try getLine

main :: IO ()
main = do
  putStrLn "Enter distance:"
  distInputResult <- safeGetLine
  case distInputResult of
    Left ioErr -> putStrLn $ "IO Error while reading distance: " ++ show ioErr
    Right distInput ->
      case parseDouble distInput of
        Left parseErr -> putStrLn parseErr
        Right distance -> do
          putStrLn "Enter time:"
          timeInputResult <- safeGetLine
          case timeInputResult of
            Left ioErr -> putStrLn $ "IO Error while reading time: " ++ show ioErr
            Right timeInput ->
              case parseDouble timeInput of
                Left parseErr -> putStrLn parseErr
                Right time -> 
                  case velocity distance time of
                    Left velErr -> putStrLn velErr
                    Right vel -> putStrLn $ "Velocity = " ++ show vel
```

---

### Explanation:

* `safeGetLine` uses `try` from `Control.Exception` to catch IO exceptions when reading input.
* `parseDouble` uses `readMaybe` to safely parse a string to `Double`, returning an `Either String Double` for error handling.
* `velocity` returns an `Either String Double`, checking for division by zero.
* In `main`, nested pattern matches handle each step's possible failure.
* If everything succeeds, velocity is printed.
* If any step fails (IO exception or parse error or logical error), a helpful error message is shown.


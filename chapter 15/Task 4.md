

### ✅ Working Example: Using a Handler Function

```haskell
-- TrafficLightHandler.hs
{-# LANGUAGE DeriveDataTypeable #-}

module Main where

import Control.Exception
import Data.Typeable

-- Define possible traffic light colors
data TrafficLight = Red | Yellow | Green deriving (Show, Read, Eq)

-- Define a custom exception
data TrafficLightException = InvalidTrafficLight String
    deriving (Show, Typeable)

instance Exception TrafficLightException

-- AI behavior based on traffic light
reactToLight :: TrafficLight -> String
reactToLight Red    = "Car stops."
reactToLight Yellow = "Car slows down."
reactToLight Green  = "Car moves forward."

-- Parse input or throw exception
parseTrafficLight :: String -> IO TrafficLight
parseTrafficLight input =
    case reads input :: [(TrafficLight, String)] of
        [(light, "")] -> return light
        _             -> throwIO (InvalidTrafficLight input)

-- Define the handler function
handleTrafficLightError :: TrafficLightException -> IO ()
handleTrafficLightError (InvalidTrafficLight input) =
    putStrLn $ "Error: Invalid traffic light color '" ++ input ++ "'"

-- Main with handler
main :: IO ()
main = handle handleTrafficLightError $ do
    putStrLn "Enter the traffic light color (Red, Yellow, Green):"
    input <- getLine
    light <- parseTrafficLight input
    putStrLn $ "Traffic Light: " ++ show light ++ " -> " ++ reactToLight light
```

---



### 🧠 Example Output

**Valid:**

```
Enter the traffic light color (Red, Yellow, Green):
Green
Traffic Light: Green -> Car moves forward.
```

**Invalid:**

```
Enter the traffic light color (Red, Yellow, Green):
Blue
Error: Invalid traffic light color 'Blue'
```

---

### 🔍 Explanation

* `handleTrafficLightError` is the **handler function**. It receives any `TrafficLightException` and prints an error message.
* `handle handler action` wraps the main logic and **automatically catches** exceptions of the matching type (`TrafficLightException`).
* `throwIO` is used to throw exceptions in the IO context (safe and recommended).

---


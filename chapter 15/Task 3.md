

### ✅ **Code Example: Custom Traffic Light Exception in Haskell**

```haskell
-- TrafficLightException.hs
{-# LANGUAGE DeriveDataTypeable #-}

module Main where

import Control.Exception
import Data.Typeable

-- Define possible traffic light colors
data TrafficLight = Red | Yellow | Green deriving (Show, Read, Eq)

-- Define a custom exception for traffic light errors
data TrafficLightException = InvalidTrafficLight String
    deriving (Show, Typeable)

instance Exception TrafficLightException

-- Define the car's response to each traffic light color
reactToLight :: TrafficLight -> String
reactToLight Red    = "Car stops."
reactToLight Yellow = "Car slows down."
reactToLight Green  = "Car moves forward."

-- Parse user input into a TrafficLight or throw custom exception
parseTrafficLight :: String -> IO TrafficLight
parseTrafficLight input =
    case reads input :: [(TrafficLight, String)] of
        [(light, "")] -> return light
        _             -> throwIO (InvalidTrafficLight input)

-- Main function with exception handling
main :: IO ()
main = do
    putStrLn "Enter the traffic light color (Red, Yellow, Green):"
    input <- getLine
    result <- try (parseTrafficLight input) :: IO (Either TrafficLightException TrafficLight)
    case result of
        Left (InvalidTrafficLight s) -> putStrLn $ "Error: Invalid traffic light color '" ++ s ++ "'"
        Right light -> putStrLn $ "Traffic Light: " ++ show light ++ " -> " ++ reactToLight light
```

---



### 🧠 Example Output

**Valid input:**

```
Enter the traffic light color (Red, Yellow, Green):
Red
Traffic Light: Red -> Car stops.
```

**Invalid input:**

```
Enter the traffic light color (Red, Yellow, Green):
Blue
Error: Invalid traffic light color 'Blue'
```

---


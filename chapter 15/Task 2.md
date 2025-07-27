

### ✅ Code Example (Self-driving AI reacting to traffic lights)

```haskell
-- SelfDrivingCar.hs
module Main where

-- Define possible traffic light colors
data TrafficLight = Red | Yellow | Green deriving (Show, Read, Eq)

-- Define the car's response to each traffic light color
reactToLight :: TrafficLight -> String
reactToLight Red    = "Car stops."
reactToLight Yellow = "Car slows down."
reactToLight Green  = "Car moves forward."

-- Main function to simulate AI behavior
main :: IO ()
main = do
    putStrLn "Enter the traffic light color (Red, Yellow, Green):"
    input <- getLine
    let maybeLight = reads input :: [(TrafficLight, String)]
    case maybeLight of
        [(light, "")] -> putStrLn $ "Traffic Light: " ++ show light ++ " -> " ++ reactToLight light
        _             -> putStrLn "Invalid traffic light color. Please enter Red, Yellow, or Green."
```

---



### 🧠 Example Output

```bash
Enter the traffic light color (Red, Yellow, Green):
Green
Traffic Light: Green -> Car moves forward.
```


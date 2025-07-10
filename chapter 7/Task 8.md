

* A `Shape` data type with constructors `Circle Double` and `Rectangle Double Double`.
* A function `parseShape :: String -> Maybe Shape` that parses a string into a `Shape`.
* Returns `Nothing` if the input is invalid (e.g., wrong keyword or incorrect number format).

---

### ✅ Haskell Code Example

```haskell
import Text.Read (readMaybe)

-- Define the Shape data type
data Shape = Circle Double | Rectangle Double Double deriving (Show)

-- Function to parse a string into a Shape
parseShape :: String -> Maybe Shape
parseShape input =
    case words input of
        ["Circle", rStr] ->
            case readMaybe rStr of
                Just r  -> Just (Circle r)
                Nothing -> Nothing
        ["Rectangle", wStr, hStr] ->
            case (readMaybe wStr, readMaybe hStr) of
                (Just w, Just h) -> Just (Rectangle w h)
                _                -> Nothing
        _ -> Nothing

-- Main function to test parseShape
main :: IO ()
main = do
    let inputs = [ "Circle 5.0"
                 , "Rectangle 4.0 6.0"
                 , "Triangle 3 4 5"
                 , "Circle five"
                 , "Rectangle 4.0"
                 ]

    mapM_ (\s -> putStrLn $ "Input: " ++ s ++ " -> " ++ show (parseShape s)) inputs
```

---

### 🧠 Explanation:

* `parseShape` uses `words` to split the input string.
* It tries to parse the numbers using `readMaybe` (safe version of `read`).
* If parsing fails or the format is incorrect, it returns `Nothing`.
* Otherwise, it returns `Just Shape`.

---

### 💡 Sample Output:

```
Input: Circle 5.0 -> Just (Circle 5.0)
Input: Rectangle 4.0 6.0 -> Just (Rectangle 4.0 6.0)
Input: Triangle 3 4 5 -> Nothing
Input: Circle five -> Nothing
Input: Rectangle 4.0 -> Nothing
```


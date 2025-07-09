HC4T1 - Task 1: Define a weatherReport Function


### ✅ Haskell Code with Explanation

```haskell
-- Function that returns a weather message based on the input condition
weatherReport :: String -> String
weatherReport "sunny"  = "It's a bright and beautiful day!"
weatherReport "rainy"  = "Don't forget your umbrella!"
weatherReport "cloudy" = "A bit gloomy, but no rain yet!"
weatherReport _        = "Weather unknown"  -- Catch-all for unrecognized input

-- Main function to test weatherReport
main :: IO ()
main = do
    putStrLn ("weatherReport \"sunny\" = " ++ weatherReport "sunny")
    putStrLn ("weatherReport \"rainy\" = " ++ weatherReport "rainy")
    putStrLn ("weatherReport \"cloudy\" = " ++ weatherReport "cloudy")
    putStrLn ("weatherReport \"foggy\" = " ++ weatherReport "foggy")
```

---

### 🧠 Explanation

* **Function signature**:

  ```haskell
  weatherReport :: String -> String
  ```

  Takes a `String` (weather condition) and returns a `String` (weather message).

* **Pattern Matching**:

  * Matches exact strings: `"sunny"`, `"rainy"`, `"cloudy"`.
  * The **underscore `_`** is a wildcard that matches any other value (used as the default).

* **`main` function**:

  * Calls `weatherReport` with different test strings and prints the results.

---


### 🖨️ Sample Output

```
weatherReport "sunny" = It's a bright and beautiful day!
weatherReport "rainy" = Don't forget your umbrella!
weatherReport "cloudy" = A bit gloomy, but no rain yet!
weatherReport "foggy" = Weather unknown
```


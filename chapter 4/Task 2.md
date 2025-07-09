HC4T2 - Task 2: Define a dayType Function

### ✅ Haskell Code with Explanation

```haskell
-- Function to classify a day as a weekday, weekend, or invalid
dayType :: String -> String
dayType "Saturday" = "It's a weekend!"
dayType "Sunday"   = "It's a weekend!"
dayType "Monday"   = "It's a weekday."
dayType "Tuesday"  = "It's a weekday."
dayType "Wednesday"= "It's a weekday."
dayType "Thursday" = "It's a weekday."
dayType "Friday"   = "It's a weekday."
dayType _          = "Invalid day"  -- For any unrecognized input

-- Main function to test dayType
main :: IO ()
main = do
    putStrLn ("dayType \"Monday\" = " ++ dayType "Monday")
    putStrLn ("dayType \"Saturday\" = " ++ dayType "Saturday")
    putStrLn ("dayType \"Sunday\" = " ++ dayType "Sunday")
    putStrLn ("dayType \"Funday\" = " ++ dayType "Funday")  -- Invalid input
```

---

### 🧠 Explanation

* **Function signature**:

  ```haskell
  dayType :: String -> String
  ```

  Takes a `String` (representing a day) and returns a `String` indicating the type of day.

* **Pattern Matching**:

  * `"Saturday"` and `"Sunday"` → Weekend
  * `"Monday"` to `"Friday"` → Weekday
  * Anything else (`_`) → Invalid day

* **Test cases** in `main` show various inputs including a valid weekday, weekend, and an invalid string.

---

### 🧪 How to Run

1. Save this code in a file named `DayType.hs`
2. Compile and run:

```bash
ghc DayType.hs -o daytype
./daytype
```

---

### 🖨️ Sample Output

```
dayType "Monday" = It's a weekday.
dayType "Saturday" = It's a weekend!
dayType "Sunday" = It's a weekend!
dayType "Funday" = Invalid day
```


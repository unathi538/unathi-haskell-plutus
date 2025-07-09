HC3T7 - Advanced Task 7: Determine the season based on the month using guards


### ✅ Haskell Code with Explanation

```haskell
-- Function to determine the season based on the month number
season :: Int -> String
season month
    | month == 12 || month == 1 || month == 2  = "Winter"
    | month == 3  || month == 4 || month == 5  = "Spring"
    | month == 6  || month == 7 || month == 8  = "Summer"
    | month == 9  || month == 10 || month == 11 = "Autumn"
    | otherwise = "Invalid month"

-- Main function to test the season function
main :: IO ()
main = do
    let s1 = season 3     -- Should be "Spring"
    let s2 = season 7     -- Should be "Summer"
    let s3 = season 11    -- Should be "Autumn"
    putStrLn ("season 3 = " ++ s1)
    putStrLn ("season 7 = " ++ s2)
    putStrLn ("season 11 = " ++ s3)
```

---

### 🧠 Explanation

* **Function Signature**:

  ```haskell
  season :: Int -> String
  ```

  Takes a month (as an `Int` from 1 to 12) and returns the name of the corresponding **season** as a `String`.

* **Guards** (`|`) are used to check which group the month falls into:

  * `12, 1, 2` → `"Winter"`
  * `3, 4, 5` → `"Spring"`
  * `6, 7, 8` → `"Summer"`
  * `9, 10, 11` → `"Autumn"`
  * `otherwise` catches invalid months (e.g., `0`, `13`)

* The `main` function calls `season` with different test months and prints the results.

---



### 🖨️ Sample Output

```
season 3 = Spring
season 7 = Summer
season 11 = Autumn
```


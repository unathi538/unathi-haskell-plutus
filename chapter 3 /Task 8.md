HC3T8 - Advanced Task 8: Calculate BMI and return category using where



### ✅ Haskell Code with Explanation

```haskell
-- Function to calculate and classify BMI
bmiCategory :: Float -> Float -> String
bmiCategory weight height
    | bmi < 18.5  = "Underweight"
    | bmi < 25    = "Normal"
    | bmi < 30    = "Overweight"
    | bmi == 30   = "Obese"
    | bmi > 30    = "Obese"
    where
        bmi = weight / (height ^ 2)  -- BMI formula: weight in kg / (height in meters)^2

-- Main function to test bmiCategory
main :: IO ()
main = do
    let result1 = bmiCategory 70 1.75   -- BMI ≈ 22.86 → Normal
    let result2 = bmiCategory 90 1.8    -- BMI ≈ 27.78 → Overweight
    putStrLn ("bmiCategory 70 1.75 = " ++ result1)
    putStrLn ("bmiCategory 90 1.8 = " ++ result2)
```

---

### 🧠 Explanation

* **Function signature**:

  ```haskell
  bmiCategory :: Float -> Float -> String
  ```

  Takes **weight** and **height**, and returns a `String` describing the BMI category.

* **Where clause**:

  * `bmi = weight / (height ^ 2)` calculates the Body Mass Index.
  * `^ 2` means height squared.

* **Guards** (`|`) check BMI ranges:

  * `< 18.5` → `"Underweight"`
  * `< 25` → `"Normal"` (includes 18.5 to 24.9)
  * `< 30` → `"Overweight"` (includes 25 to 29.9)
  * `== 30` and `> 30` → `"Obese"`

---



### 🖨️ Sample Output

```
bmiCategory 70 1.75 = Normal
bmiCategory 90 1.8 = Overweight
```


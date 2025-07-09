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
        bmi = weight / height^2  -- BMI calculation: weight in kg, height in meters
        -- height^2 is height squared
        -- weight / height^2 gives BMI in kg/m²

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

* **Function Signature**:

  ```haskell
  bmiCategory :: Float -> Float -> String
  ```

  The function takes `weight` (in kilograms) and `height` (in meters), and returns a `String` indicating the BMI category.

* **`where` clause**:

  * Used to **define `bmi` locally** within the function scope.
  * Formula used: `bmi = weight / height^2`.

* **Guards**:

  * Use multiple conditions to check the BMI value and return the correct category:

    * `< 18.5` → "Underweight"
    * `< 25` → "Normal"
    * `< 30` → "Overweight"
    * `== 30` or `> 30` → "Obese"

---



### 🖨️ Sample Output

```
bmiCategory 70 1.75 = Normal
bmiCategory 90 1.8 = Overweight
```


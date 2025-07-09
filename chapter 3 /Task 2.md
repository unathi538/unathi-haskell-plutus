HC3T2 - Task 2: Determine the grade based on a score using guards



---

### ✅ **Haskell Code with Explanations**

```haskell
-- Define the function 'grade' with a type signature:
-- It takes an Int (score) and returns a String (the letter grade)
grade :: Int -> String
grade score
    -- Use guards to check conditions in order
    | score >= 90 = "A"        -- If score is 90 or more, grade is "A"
    | score >= 80 = "B"        -- If score is 80–89, grade is "B"
    | score >= 70 = "C"        -- If score is 70–79, grade is "C"
    | score >= 60 = "D"        -- If score is 60–69, grade is "D"
    | otherwise   = "F"        -- If score is below 60, grade is "F"

-- Main function to test the grade function with different scores
main :: IO ()
main = do
    -- Test with a high score (should be A)
    putStrLn ("grade 95 = " ++ grade 95)

    -- Test with a middle score (should be C)
    putStrLn ("grade 72 = " ++ grade 72)

    -- Test with a low score (should be F)
    putStrLn ("grade 50 = " ++ grade 50)
```

---

### 🧠 **Explanation**

* `grade :: Int -> String`: This is a **type signature**. It says that the function `grade` takes an `Int` and returns a `String`.

* `grade score` uses **guards** (`|`) to check multiple conditions:

  * Haskell checks the conditions **top to bottom**.
  * If a condition is true, it returns the corresponding grade.
  * `otherwise` is just a synonym for `True`, acting as the default fallback case.

* The `main` function uses `putStrLn` to **print the result** of calling `grade` with different test values.

---

### 🖨️ Expected Output When Run

```
grade 95 = A
grade 72 = C
grade 50 = F
```

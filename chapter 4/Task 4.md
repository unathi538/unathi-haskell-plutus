HC4T4 - Task 4: Rewrite specialBirthday using Pattern Matching



### ✅ Haskell Code with Explanation

```haskell
-- Function to return a comment based on a numerical grade
gradeComment :: Int -> String
gradeComment grade
    | grade >= 90 && grade <= 100 = "Excellent!"
    | grade >= 70 && grade <= 89  = "Good job!"
    | grade >= 50 && grade <= 69  = "You passed."
    | grade >= 0  && grade <= 49  = "Better luck next time."
    | otherwise                   = "Invalid grade"

-- Main function to test gradeComment
main :: IO ()
main = do
    putStrLn ("gradeComment 95 = " ++ gradeComment 95)
    putStrLn ("gradeComment 75 = " ++ gradeComment 75)
    putStrLn ("gradeComment 60 = " ++ gradeComment 60)
    putStrLn ("gradeComment 30 = " ++ gradeComment 30)
    putStrLn ("gradeComment 110 = " ++ gradeComment 110)  -- Invalid
```

---

### 🧠 Explanation

* **Function signature**:

  ```haskell
  gradeComment :: Int -> String
  ```

  The function takes an integer `grade` and returns a corresponding `String` comment.

* **Guards** (`|`) are used to match ranges:

  * `90–100` → "Excellent!"
  * `70–89` → "Good job!"
  * `50–69` → "You passed."
  * `0–49` → "Better luck next time."
  * Any number outside `0–100` → "Invalid grade"

---



### 🖨️ Sample Output

```
gradeComment 95 = Excellent!
gradeComment 75 = Good job!
gradeComment 60 = You passed.
gradeComment 30 = Better luck next time.
gradeComment 110 = Invalid grade
```


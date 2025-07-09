C3T9 - Advanced Task 9: Find the maximum of three numbers using let


### ✅ Haskell Code with Explanation

```haskell
-- Function to find the maximum of three Int values
maxOfThree :: Int -> Int -> Int -> Int
maxOfThree a b c =
    let maxAB = max a b     -- Find the maximum of a and b
        maxABC = max maxAB c  -- Compare the result with c
    in maxABC               -- Return the final maximum

-- Main function to test maxOfThree
main :: IO ()
main = do
    let result1 = maxOfThree 10 20 15   -- Should return 20
    let result2 = maxOfThree 5 25 10    -- Should return 25
    putStrLn ("maxOfThree 10 20 15 = " ++ show result1)
    putStrLn ("maxOfThree 5 25 10 = " ++ show result2)
```

---

### 🧠 Explanation

* **Function Signature**:

  ```haskell
  maxOfThree :: Int -> Int -> Int -> Int
  ```

  The function takes three `Int` values and returns the **maximum** among them.

* **`let` Bindings**:

  * `maxAB = max a b` finds the maximum of the first two inputs.
  * `maxABC = max maxAB c` compares that result to the third number.
  * The final result (`maxABC`) is returned as the maximum of all three numbers.

* **`main`** tests:

  * `maxOfThree 10 20 15` → should return `20`
  * `maxOfThree 5 25 10` → should return `25`

---



### 🖨️ Sample Output

```
maxOfThree 10 20 15 = 20
maxOfThree 5 25 10 = 25
```


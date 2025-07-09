HC3T4 - Task 4: Calculate the area of a triangle using Heron's formula



### ✅ **Haskell Code with Explanation**

```haskell
-- Function to calculate the area of a triangle using Heron's formula
triangleArea :: Float -> Float -> Float -> Float

-- Main function to test triangleArea
main :: IO ()
main = do
    let area1 = triangleArea 3 4 5   -- Right-angled triangle, should be 6.0
    let area2 = triangleArea 7 8 9   -- Scalene triangle
    putStrLn ("triangleArea 3 4 5 = " ++ show area1)
    putStrLn ("triangleArea 7 8 9 = " ++ show area2)
```

---

### 🧠 Explanation

* **Function Signature**:

  ```haskell
  triangleArea :: Float -> Float -> Float -> Float
  ```

  This means `triangleArea` takes three `Float` values (sides of a triangle) and returns a `Float` (the area).

* **`let` bindings**:

  * `s` is the **semi-perimeter** of the triangle:
    $s = \frac{a + b + c}{2}$
  * `area` applies **Heron's formula**:
    $\text{area} = \sqrt{s(s-a)(s-b)(s-c)}$

* **`main`**:

  * Tests the function with two triangle side sets:

    * `(3, 4, 5)` → Right triangle (area = 6)
    * `(7, 8, 9)` → General triangle

---


### 🖨️ Sample Output

```
triangleArea 3 4 5 = 6.0
triangleArea 7 8 9 = 26.832815
```


HC3T5 - Task 5: Determine the type of a triangle using guards



### ✅ Haskell Code with Explanation

```haskell
-- Function to classify a triangle based on its side lengths
triangleType :: Float -> Float -> Float -> String
triangleType a b c
    | a == b && b == c            = "Equilateral"  -- All three sides are equal
    | a == b || b == c || a == c  = "Isosceles"    -- Two sides are equal
    | otherwise                   = "Scalene"      -- No sides are equal

-- Main function to test triangleType
main :: IO ()
main = do
    let t1 = triangleType 3 3 3     -- All sides equal
    let t2 = triangleType 5 5 8     -- Two sides equal
    let t3 = triangleType 6 7 8     -- All sides different
    putStrLn ("triangleType 3 3 3 = " ++ t1)
    putStrLn ("triangleType 5 5 8 = " ++ t2)
    putStrLn ("triangleType 6 7 8 = " ++ t3)
```

---

### 🧠 Explanation

* **Function Signature**:

  ```haskell
  triangleType :: Float -> Float -> Float -> String
  ```

  This means `triangleType` takes three side lengths (as `Float`) and returns a description (`String`) of the triangle type.

* **Guards** (`|`) are used to check:

  * **Equilateral**: All three sides are equal
  * **Isosceles**: Exactly two sides are equal
  * **Scalene**: All three sides are different (`otherwise` covers this case)

* **Main** function tests:

  * `triangleType 3 3 3` → `"Equilateral"`
  * `triangleType 5 5 8` → `"Isosceles"`
  * `triangleType 6 7 8` → `"Scalene"`

---

### 🧪 How to Run

1. Save this code in a file named `TriangleType.hs`
2. Compile and run:

```bash
ghc TriangleType.hs -o triangletype
./triangletype
```

---

### 🖨️ Sample Output

```
triangleType 3 3 3 = Equilateral
triangleType 5 5 8 = Isosceles
triangleType 6 7 8 = Scalene
```



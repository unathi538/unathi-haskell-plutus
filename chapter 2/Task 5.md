HC2T5 - Task 5: Defining and Using Functions


1. `circleArea` – a function that calculates the area of a circle from a `Float` radius.
2. `maxOfThree` – a function that returns the maximum of three `Int` values.

The program includes a `main` function to run and display test results.

---

### ✅ Haskell Code

```haskell
-- Function to calculate the area of a circle
circleArea :: Float -> Float
circleArea radius = pi * radius * radius
-- Explanation: Area = π * r^2

-- Function to find the maximum of three Ints
maxOfThree :: Int -> Int -> Int -> Int
maxOfThree x y z = max x (max y z)
-- Explanation: max y z gives the larger of y and z, then max x (that result)

-- Main function to test both
main :: IO ()
main = do
    putStrLn "Testing circleArea:"
    print $ circleArea 5.0     -- Should be 78.53982
    print $ circleArea 2.5     -- Should be 19.634954
    print $ circleArea 0       -- Should be 0.0

    putStrLn "\nTesting maxOfThree:"
    print $ maxOfThree 10 20 15   -- Should be 20
    print $ maxOfThree 5 5 5      -- Should be 5
    print $ maxOfThree (-1) 0 (-3) -- Should be 0
```

---

### 🧪 Sample Output When Run

```
Testing circleArea:
78.53982
19.634954
0.0

Testing maxOfThree:
20
5
0
```

---

explanation

* `pi` is a predefined constant in Haskell for the value of π.
* `max` is a built-in function that returns the larger of two values.
* This code runs correctly in GHC or any Haskell interpreter.



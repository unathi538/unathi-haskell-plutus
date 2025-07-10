

### ✅ Haskell Code Example

```haskell
-- Function to calculate the circumference of a circle
circleCircumference :: (Real a) => a -> Double
circleCircumference r = 2 * pi * (realToFrac r)

-- Main function to test circleCircumference
main :: IO ()
main = do
    let radiusInt = 5 :: Int
    let radiusFloat = 4.5 :: Float
    let radiusDouble = 7.25 :: Double

    putStrLn $ "Circumference with Int radius 5: " ++ show (circleCircumference radiusInt)
    putStrLn $ "Circumference with Float radius 4.5: " ++ show (circleCircumference radiusFloat)
    putStrLn $ "Circumference with Double radius 7.25: " ++ show (circleCircumference radiusDouble)
```

---

### 🧠 Explanation:

* `circleCircumference :: (Real a) => a -> Double`:

  * Accepts any `Real` type (e.g., `Int`, `Integer`, `Float`, `Double`).
  * Uses `realToFrac` to convert the input to a `Double` so we can use `pi` and floating-point math.
* `2 * pi * r` is the formula for the circumference of a circle.

---

### 💡 Sample Output:

```
Circumference with Int radius 5: 31.41592653589793
Circumference with Float radius 4.5: 28.274333882308138
Circumference with Double radius 7.25: 45.553093477052
```



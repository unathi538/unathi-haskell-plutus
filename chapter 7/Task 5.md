

### ✅ Haskell Code Example

```haskell
-- Function to calculate the area of a square
squareArea :: Num a => a -> a
squareArea side = side * side

-- Main function to test squareArea
main :: IO ()
main = do
    let intSide = 5 :: Int
    let floatSide = 4.5 :: Float
    let doubleSide = 6.25 :: Double

    putStrLn $ "Area of square with Int side 5: " ++ show (squareArea intSide)
    putStrLn $ "Area of square with Float side 4.5: " ++ show (squareArea floatSide)
    putStrLn $ "Area of square with Double side 6.25: " ++ show (squareArea doubleSide)
```

---

### 🧠 Explanation:

* `squareArea :: Num a => a -> a`
  This means `squareArea` works for any type `a` that is an instance of the `Num` type class.
* The function simply multiplies the side length by itself (`side * side`).
* Demonstrates usage with `Int`, `Float`, and `Double`.

---

### 💡 Sample Output:

```
Area of square with Int side 5: 25
Area of square with Float side 4.5: 20.25
Area of square with Double side 6.25: 39.0625
```


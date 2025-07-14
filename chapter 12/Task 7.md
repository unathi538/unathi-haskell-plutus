Here's a complete Haskell program that defines a function `calculateCircleArea` to compute the area of a circle given its radius. The `main` function demonstrates its usage:

```haskell
-- CircleArea.hs

-- Define the function to calculate the area of a circle
calculateCircleArea :: Floating a => a -> a
calculateCircleArea radius = pi * radius * radius

-- Main function to demonstrate usage
main :: IO ()
main = do
    let radius = 5.0
    let area = calculateCircleArea radius
    putStrLn ("The area of a circle with radius " ++ show radius ++ " is " ++ show area)
```

---

### ✅ How to Run:

1. Save this code in a file called `CircleArea.hs`.
2. Run with:

```bash
runghc CircleArea.hs
```

---

### 💡 Output:

```
The area of a circle with radius 5.0 is 78.53981633974483
```



HC1T2 - Task 2: Pure Function Example


```haskell
-- Define the function to calculate the area of a circle
circleArea :: Floating a => a -> a
circleArea r = pi * r * r

-- Main function to test the circleArea function
main :: IO ()
main = do
    let radius = 3.0
    putStrLn ("Radius: " ++ show radius)
    putStrLn ("Area of circle: " ++ show (circleArea radius))
```

### Explanation:

* `circleArea` is **pure**: it only uses the input `r` and the constant `pi`, with no side effects or external dependencies.
* `Floating a => a -> a` allows it to work with any floating-point type (`Float`, `Double`, etc.).
* `main` demonstrates using the function with a test radius of `3.0`.

### Sample Output:

```
Radius: 3.0
Area of circle: 28.274333882308138
```






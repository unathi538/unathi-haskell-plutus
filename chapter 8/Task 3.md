

* Defines a `Shape` type with constructors for `Circle` and `Rectangle`.
* Implements a function `area :: Shape -> Float` to compute the area.
* Calculates the area for:

  * A circle with radius `5`
  * A rectangle with sides `10` and `5`

---

### ✅ Haskell Code Example

```haskell
-- Define the Shape data type
data Shape = Circle Float | Rectangle Float Float deriving (Show)

-- Function to calculate the area of a Shape
area :: Shape -> Float
area (Circle r) = pi * r * r
area (Rectangle w h) = w * h

-- Main function to test the area function
main :: IO ()
main = do
    let shape1 = Circle 5
    let shape2 = Rectangle 10 5

    putStrLn $ "Shape1: " ++ show shape1 ++ ", Area: " ++ show (area shape1)
    putStrLn $ "Shape2: " ++ show shape2 ++ ", Area: " ++ show (area shape2)
```

---

### 💡 Sample Output:

```
Shape1: Circle 5.0, Area: 78.53982
Shape2: Rectangle 10.0 5.0, Area: 50.0
```

---

### 🧠 Explanation:

* `pi * r * r` calculates the area of a circle.
* `w * h` calculates the area of a rectangle.
* The `area` function uses **pattern matching** on the `Shape` type.


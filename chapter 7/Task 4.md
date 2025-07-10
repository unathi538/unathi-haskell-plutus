

### ✅ Haskell Code Example

```haskell
-- Define the Shape data type
data Shape = Circle Double | Rectangle Double Double

-- Implement Show for Shape
instance Show Shape where
    show (Circle r) = "Circle " ++ show r
    show (Rectangle w h) = "Rectangle " ++ show w ++ " " ++ show h

-- Implement Read for Shape
instance Read Shape where
    readsPrec _ input =
        case words input of
            ("Circle":r:_) ->
                [(Circle (read r), "")]
            ("Rectangle":w:h:_) ->
                [(Rectangle (read w) (read h), "")]
            _ -> []

-- Main function to test Shape
main :: IO ()
main = do
    let shape1 = Circle 5.5
    let shape2 = Rectangle 4.0 6.0

    -- Show shapes
    putStrLn $ "Shape1: " ++ show shape1
    putStrLn $ "Shape2: " ++ show shape2

    -- Read shapes from strings
    let shapeStr1 = "Circle 5.5"
    let shapeStr2 = "Rectangle 4.0 6.0"

    let parsedShape1 = read shapeStr1 :: Shape
    let parsedShape2 = read shapeStr2 :: Shape

    putStrLn $ "Parsed Shape1: " ++ show parsedShape1
    putStrLn $ "Parsed Shape2: " ++ show parsedShape2
```

---

### 🧠 Explanation:

* `Shape` is a data type with:

  * `Circle Double` → represents a circle with a radius.
  * `Rectangle Double Double` → represents a rectangle with width and height.
* `Show` instance: converts `Shape` to a readable string.
* `Read` instance: parses a string like `"Circle 5.5"` or `"Rectangle 4.0 6.0"` into a `Shape`.

---

### 💡 Sample Output:

```
Shape1: Circle 5.5
Shape2: Rectangle 4.0 6.0
Parsed Shape1: Circle 5.5
Parsed Shape2: Rectangle 4.0 6.0
```




### ✅ **Full Example**

```haskell
-- Define the parametric Shape data type
data Shape a = Circle a | Rectangle a deriving Show

-- Example usage in main
main :: IO ()
main = do
    -- Create shapes with color as a String
    let redCircle = Circle "Red"
    let blueRectangle = Rectangle "Blue"

    putStrLn "Shapes with color (String):"
    print redCircle
    print blueRectangle

    -- Create shapes with color as an Int (e.g., RGB code)
    let circleRGB = Circle (255 :: Int)
    let rectRGB = Rectangle (128 :: Int)

    putStrLn "\nShapes with color (Int RGB codes):"
    print circleRGB
    print rectRGB
```

---

### 🔍 Explanation

* `data Shape a = Circle a | Rectangle a` defines a **parametric** data type.

  * The type parameter `a` allows you to specify the type of the color (e.g., `String`, `Int`, etc.).
* `deriving Show` allows printing with `print`.
* The `main` function demonstrates usage with both `String` and `Int` as color types.

---

### 💡 Sample Output

```
Shapes with color (String):
Circle "Red"
Rectangle "Blue"

Shapes with color (Int RGB codes):
Circle 255
Rectangle 128
```


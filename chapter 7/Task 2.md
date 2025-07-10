

### ✅ Haskell Code Example

```haskell
-- Define the Color data type
data Color = Red | Green | Blue

-- Implement the Eq type class for Color
instance Eq Color where
    Red   == Red   = True
    Green == Green = True
    Blue  == Blue  = True
    _     == _     = False

-- Allow Color to be shown as a string
instance Show Color where
    show Red   = "Red"
    show Green = "Green"
    show Blue  = "Blue"

-- Main function to test Color equality
main :: IO ()
main = do
    let color1 = Red
    let color2 = Green
    let color3 = Red

    putStrLn $ show color1 ++ " == " ++ show color2 ++ " -> " ++ show (color1 == color2)
    putStrLn $ show color1 ++ " == " ++ show color3 ++ " -> " ++ show (color1 == color3)
```

---

### 🧠 Explanation:

* `data Color = Red | Green | Blue` defines a custom type with 3 values.
* The `Eq` instance is implemented manually to specify when two `Color` values are equal.
* A `Show` instance is also implemented so the colors can be printed in `main`.

---

### 💡 Sample Output:

```
Red == Green -> False
Red == Red -> True
```


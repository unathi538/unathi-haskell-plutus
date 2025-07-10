

* A custom data type `Color` with values `Red`, `Green`, and `Blue`.
* A function `nextColor` that returns the next color in sequence.
* When the color is `Blue`, it wraps around to `Red`.

---

### ✅ Haskell Code Example

```haskell
-- Define the Color data type
data Color = Red | Green | Blue deriving (Show, Read, Eq)

-- Define the nextColor function
nextColor :: Color -> Color
nextColor Red   = Green
nextColor Green = Blue
nextColor Blue  = Red  -- wrap around

-- Main function to test nextColor
main :: IO ()
main = do
    let c1 = Red
    let c2 = nextColor c1
    let c3 = nextColor c2
    let c4 = nextColor c3

    putStrLn $ "Starting color: " ++ show c1
    putStrLn $ "Next color: " ++ show c2
    putStrLn $ "Next color: " ++ show c3
    putStrLn $ "Next color: " ++ show c4
```

---

### 🧠 Explanation:

* `nextColor` maps `Red -> Green`, `Green -> Blue`, and `Blue -> Red`.
* `deriving (Show, Read, Eq)` allows the type to be printed, parsed from strings, and compared.

---

### 💡 Sample Output:

```
Starting color: Red
Next color: Green
Next color: Blue
Next color: Red
```



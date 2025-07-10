

* A **type class** `Describable` with a method `describe`
* **Instances** of `Describable` for:

  * `Bool`
  * A custom data type `Shape` with `Circle` and `Rectangle`

---

### ✅ Haskell Code Example

```haskell
-- Define the Shape data type
data Shape = Circle Double | Rectangle Double Double deriving (Show)

-- Define the Describable type class
class Describable a where
    describe :: a -> String

-- Implement Describable for Bool
instance Describable Bool where
    describe True  = "This is true."
    describe False = "This is false."

-- Implement Describable for Shape
instance Describable Shape where
    describe (Circle r) = "A circle with radius " ++ show r
    describe (Rectangle w h) = "A rectangle with width " ++ show w ++ " and height " ++ show h

-- Main function to test Describable
main :: IO ()
main = do
    let b1 = True
    let b2 = False
    let s1 = Circle 3.5
    let s2 = Rectangle 4 5

    putStrLn $ "Bool True: " ++ describe b1
    putStrLn $ "Bool False: " ++ describe b2
    putStrLn $ "Shape Circle: " ++ describe s1
    putStrLn $ "Shape Rectangle: " ++ describe s2
```

---

### 🧠 Explanation:

* `class Describable a where describe :: a -> String`:
  Defines a type class with a `describe` method that returns a string description of the value.
* `instance Describable Bool` provides behavior for `True` and `False`.
* `instance Describable Shape` customizes output for `Circle` and `Rectangle`.

---

### 💡 Sample Output:

```
Bool True: This is true.
Bool False: This is false.
Shape Circle: A circle with radius 3.5
Shape Rectangle: A rectangle with width 4.0 and height 5.0
```


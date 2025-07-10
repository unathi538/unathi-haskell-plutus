To represent different kinds of shapes (like **Circle** and **Rectangle**) with different fields but under a single `Shape` type in Haskell, we **can’t use record syntax alone** on a single constructor—because circles and rectangles have different fields.


---

### ✅ Working Haskell Code Example

```haskell
-- Define the Shape type with Circle and Rectangle constructors
data Shape
  = Circle
      { center :: (Float, Float)
      , radius :: Float
      , color  :: String
      }
  | Rectangle
      { topLeft :: (Float, Float)
      , width   :: Float
      , height  :: Float
      , color   :: String
      }
  deriving (Show)

-- Create a Circle instance
circleShape :: Shape
circleShape = Circle
  { center = (0.0, 0.0)
  , radius = 5.0
  , color  = "Red"
  }

-- Create a Rectangle instance
rectangleShape :: Shape
rectangleShape = Rectangle
  { topLeft = (10.0, 20.0)
  , width   = 15.0
  , height  = 25.0
  , color   = "Blue"
  }

-- Main function to display the shapes
main :: IO ()
main = do
  putStrLn "Circle Shape:"
  print circleShape

  putStrLn "\nRectangle Shape:"
  print rectangleShape
```

---

### 🧠 Explanation:

* `Shape` is a **sum type** with two constructors:

  * `Circle` has fields: `center`, `radius`, and `color`.
  * `Rectangle` has fields: `topLeft` (position), `width`, `height`, and `color`.
* Each constructor uses **record syntax**, allowing you to name fields.
* In `main`, we define and print one circle and one rectangle.

---

### 💡 Sample Output:

```
Circle Shape:
Circle {center = (0.0,0.0), radius = 5.0, color = "Red"}

Rectangle Shape:
Rectangle {topLeft = (10.0,20.0), width = 15.0, height = 25.0, color = "Blue"}
```



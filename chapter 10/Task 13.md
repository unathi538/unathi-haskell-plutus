
* Defines a `Box a` type with two constructors: `Empty` and `Has a`,
* Defines a type class `Container` with the methods:

  * `isEmpty :: c a -> Bool`,
  * `contains :: Eq a => c a -> a -> Bool`,
  * `replace  :: c a -> a -> c a`,
* Implements a `Container` instance for `Box`,
* Demonstrates all three methods in `main`.

---

### ✅ Full Example

```haskell
-- Define the Box type
data Box a = Empty | Has a deriving (Show, Eq)

-- Define the Container type class
class Container c where
  isEmpty  :: c a -> Bool
  contains :: Eq a => c a -> a -> Bool
  replace  :: c a -> a -> c a

-- Implement Container for Box
instance Container Box where
  isEmpty Empty     = True
  isEmpty (Has _)   = False

  contains (Has x) val = x == val
  contains Empty _     = False

  replace _ newVal = Has newVal

-- Main function to demonstrate
main :: IO ()
main = do
  let box1 = Has 10
  let box2 = Empty :: Box Int

  putStrLn "Testing isEmpty:"
  print (isEmpty box1)  -- False
  print (isEmpty box2)  -- True

  putStrLn "\nTesting contains:"
  print (contains box1 10)  -- True
  print (contains box1 5)   -- False
  print (contains box2 10)  -- False

  putStrLn "\nTesting replace:"
  let box3 = replace box1 99
  print box3  -- Has 99
  let box4 = replace box2 42
  print box4  -- Has 42
```

---

### 💡 Output

```
Testing isEmpty:
False
True

Testing contains:
True
False
False

Testing replace:
Has 99
Has 42
```

---

### 🔍 Explanation

* `Container` is a generic type class for container-like structures.
* `Box` is a simple container that may be `Empty` or hold a value with `Has`.
* `replace` works on both empty and full boxes, always returns `Has newValue`.



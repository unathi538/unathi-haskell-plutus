

* Defines a `Present a` type (similar to `Box` but only one constructor holding a value),
* Defines the `Container` type class with `isEmpty`, `contains`, and `replace`,
* Implements `Container` instance for `Present`,
* Includes a `main` function demonstrating usage.

---

### ✅ Full Working Example

```haskell
-- Define the Present type (always holds a value)
newtype Present a = Present a deriving (Show, Eq)

-- Define the Container type class
class Container c where
  isEmpty  :: c a -> Bool
  contains :: Eq a => c a -> a -> Bool
  replace  :: c a -> a -> c a

-- Implement Container for Present
instance Container Present where
  isEmpty _ = False  -- Present always holds a value

  contains (Present x) val = x == val

  replace _ newVal = Present newVal

-- Main function to demonstrate
main :: IO ()
main = do
  let p1 = Present 10
  putStrLn "Testing isEmpty on Present:"
  print (isEmpty p1)  -- False

  putStrLn "\nTesting contains on Present:"
  print (contains p1 10)  -- True
  print (contains p1 5)   -- False

  putStrLn "\nTesting replace on Present:"
  let p2 = replace p1 99
  print p2  -- Present 99
```

---

### Explanation

* `Present` is a wrapper always containing a value (no empty state).
* `isEmpty` always returns `False`.
* `contains` checks equality of contained value.
* `replace` replaces the contained value.

---

### Sample Output

```
Testing isEmpty on Present:
False

Testing contains on Present:
True
False

Testing replace on Present:
Present 99
```

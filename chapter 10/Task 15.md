
* Uses the previously defined `Container` type class,
* Defines a polymorphic function `guessWhatsInside` that takes any container and a value to check for,
* Demonstrates it in `main` with both `Box` and `Present` types.

---

### ✅ Full Working Example

```haskell
-- Define the Box type
data Box a = Empty | Has a deriving (Show, Eq)

-- Define the Present type
newtype Present a = Present a deriving (Show, Eq)

-- Define the Container type class
class Container c where
  isEmpty  :: c a -> Bool
  contains :: Eq a => c a -> a -> Bool
  replace  :: c a -> a -> c a

-- Container instance for Box
instance Container Box where
  isEmpty Empty     = True
  isEmpty (Has _)   = False

  contains (Has x) val = x == val
  contains Empty _     = False

  replace _ newVal = Has newVal

-- Container instance for Present
instance Container Present where
  isEmpty _ = False
  contains (Present x) val = x == val
  replace _ newVal = Present newVal

-- guessWhatsInside function
guessWhatsInside :: (Container c, Eq a) => c a -> a -> Bool
guessWhatsInside container val = contains container val

-- Main function demonstrating usage
main :: IO ()
main = do
  let box1 = Has 42
  let box2 = Empty :: Box Int
  let present1 = Present 42

  putStrLn "Check if 42 is inside box1:"
  print $ guessWhatsInside box1 42  -- True

  putStrLn "Check if 5 is inside box1:"
  print $ guessWhatsInside box1 5   -- False

  putStrLn "Check if 42 is inside box2 (Empty):"
  print $ guessWhatsInside box2 42  -- False

  putStrLn "Check if 42 is inside present1:"
  print $ guessWhatsInside present1 42  -- True
```

---

### Explanation

* `guessWhatsInside` is polymorphic over any `Container c` holding elements of type `a` (which must support equality).
* It uses the `contains` method of the `Container` type class to check for membership.
* The `main` demonstrates it on both `Box` (which can be empty) and `Present` (always holds a value).

---

### Sample Output

```
Check if 42 is inside box1:
True
Check if 5 is inside box1:
False
Check if 42 is inside box2 (Empty):
False
Check if 42 is inside present1:
True
```


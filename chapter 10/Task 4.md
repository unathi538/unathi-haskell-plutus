

* Defines a parameterized type `Box a`,
* Makes `Box a` an instance of `Eq` (requiring `a` itself to be `Eq`),
* Includes a `main` function demonstrating equality checks.

```haskell
-- Define the parameterized Box type
data Box a = Empty | Has a deriving Show

-- Make Box an instance of Eq
instance Eq a => Eq (Box a) where
  Empty   == Empty   = True
  Has x   == Has y   = x == y
  _       == _       = False

-- Main function to demonstrate
main :: IO ()
main = do
  let box1 = Has 5
  let box2 = Has 5
  let box3 = Has 10
  let boxEmpty1 = Empty :: Box Int
  let boxEmpty2 = Empty :: Box Int

  putStrLn "box1 == box2:"
  print (box1 == box2)  -- True

  putStrLn "box1 == box3:"
  print (box1 == box3)  -- False

  putStrLn "boxEmpty1 == boxEmpty2:"
  print (boxEmpty1 == boxEmpty2)  -- True

  putStrLn "box1 == boxEmpty1:"
  print (box1 == boxEmpty1)  -- False
```

---

### Explanation:

* `Box a` is either `Empty` or `Has a`.
* `Eq` instance compares two `Box`es by:

  * `Empty` equals `Empty`,
  * `Has x` equals `Has y` if `x == y`,
  * Otherwise, unequal.
* `main` tests various cases and prints results.

---

### Sample output:

```
box1 == box2:
True
box1 == box3:
False
boxEmpty1 == boxEmpty2:
True
box1 == boxEmpty1:
False
```


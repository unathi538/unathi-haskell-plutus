
* Defines a parameterized `Box a` type with constructors `Empty` and `Has a`,
* Implements an `Ord` instance for `Box a` using the `compare` function,
* Includes a `main` function demonstrating comparisons.

---

### ✅ Full Working Example

```haskell
-- Define the Box type
data Box a = Empty | Has a deriving (Show, Eq)

-- Implement Ord instance for Box a
instance Ord a => Ord (Box a) where
  compare Empty Empty = EQ
  compare Empty (Has _) = LT
  compare (Has _) Empty = GT
  compare (Has x) (Has y) = compare x y

-- Main function to demonstrate usage
main :: IO ()
main = do
  let box1 = Has 10
  let box2 = Has 20
  let boxEmpty = Empty :: Box Int

  putStrLn $ "Compare box1 and box2: " ++ show (compare box1 box2)   -- LT
  putStrLn $ "Compare box2 and box1: " ++ show (compare box2 box1)   -- GT
  putStrLn $ "Compare box1 and box1: " ++ show (compare box1 box1)   -- EQ
  putStrLn $ "Compare boxEmpty and box1: " ++ show (compare boxEmpty box1) -- LT
  putStrLn $ "Compare boxEmpty and Empty: " ++ show (compare boxEmpty Empty) -- EQ
```

---

### Explanation

* `Empty` is considered less than any `Has` value.
* Two `Has` boxes are compared by their contained values.
* `main` tests all cases and prints results.

---

### Sample Output

```
Compare box1 and box2: LT
Compare box2 and box1: GT
Compare box1 and box1: EQ
Compare boxEmpty and box1: LT
Compare boxEmpty and Empty: EQ
```


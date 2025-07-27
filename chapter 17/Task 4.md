
## ✅ Full Working Code

```haskell
-- Define the Sum newtype
newtype Sum a = Sum a deriving (Show, Eq)

-- Semigroup instance: combine two Sum values using addition
instance Num a => Semigroup (Sum a) where
  Sum x <> Sum y = Sum (x + y)

-- Monoid instance: identity element is 0
instance Num a => Monoid (Sum a) where
  mempty = Sum 0

main :: IO ()
main = do
  let a = Sum 10
      b = Sum 5

  putStrLn "Demonstrating Sum monoid:"
  putStrLn $ "Sum 10 <> Sum 5 = " ++ show (a <> b)
  putStrLn $ "Sum 10 <> mempty = " ++ show (a <> mempty)
  putStrLn $ "mempty <> Sum 5 = " ++ show (mempty <> b)
```

---

## 🔍 Explanation

### 🔹 `newtype Sum a`

* Wraps a numeric value `a` (like `Int`, `Float`, etc.).
* The `Num a` constraint ensures that we can add values of type `a`.

### 🔹 `Semigroup` instance

* Uses `+` to combine two `Sum` values.

### 🔹 `Monoid` instance

* Defines `mempty = Sum 0` as the **identity element** (adding 0 changes nothing).

### 🔹 `main`

* Demonstrates how `Sum` behaves with `<>` (the Semigroup/Monoid operator).
* Verifies that `mempty` behaves as expected.

---




## ✅ Full Working Code

```haskell
-- Define Min newtype wrapper
newtype Min a = Min a deriving (Show, Eq, Ord)

-- Define Max newtype wrapper
newtype Max a = Max a deriving (Show, Eq, Ord)

-- Semigroup instance for Min: keeps the smallest value
instance Ord a => Semigroup (Min a) where
  Min x <> Min y = Min (min x y)

-- Semigroup instance for Max: keeps the largest value
instance Ord a => Semigroup (Max a) where
  Max x <> Max y = Max (max x y)

-- Optional: Monoid instances
instance (Ord a, Bounded a) => Monoid (Min a) where
  mempty = Min maxBound

instance (Ord a, Bounded a) => Monoid (Max a) where
  mempty = Max minBound

main :: IO ()
main = do
  let a = Min 10
      b = Min 7
      c = Max 10
      d = Max 7

  putStrLn $ "Min 10 <> Min 7 = " ++ show (a <> b)  -- should be Min 7
  putStrLn $ "Max 10 <> Max 7 = " ++ show (c <> d)  -- should be Max 10

  putStrLn $ "Min 7 <> mempty = " ++ show (b <> mempty)  -- Monoid identity test
  putStrLn $ "Max 7 <> mempty = " ++ show (d <> mempty)
```

---

## 🔍 Explanation

### ✅ `newtype Min a` and `Max a`

* These wrap a value of type `a` (e.g. `Int`, `Double`, etc.)
* The `Ord` constraint is required so we can use `min` and `max`.

### ✅ `Semigroup` Instances

* `Min x <> Min y = Min (min x y)` — keeps the smaller value.
* `Max x <> Max y = Max (max x y)` — keeps the larger value.

### ✅ `Monoid` Instances (optional but useful)

* Use `Bounded`:

  * `Min` uses `maxBound` as identity (because `min x maxBound = x`)
  * `Max` uses `minBound` as identity

### ✅ `main`

* Demonstrates combining `Min` and `Max` values with `<>` (Semigroup).
* Shows behavior when using `mempty` (Monoid).

---


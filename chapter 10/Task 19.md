

* Defines a `Length` data type with constructors `M` (meters) and `Km` (kilometers),
* Derives `Eq` automatically,
* Manually implements `Ord` to correctly compare lengths by converting kilometers to meters internally,
* Includes a `main` function demonstrating comparisons.

---

### ✅ Full Working Example

```haskell
-- Define Length type with meters (M) and kilometers (Km)
data Length = M Double | Km Double deriving (Show, Eq)

-- Implement Ord manually to handle unit conversion
instance Ord Length where
  compare (M m1) (M m2)     = compare m1 m2
  compare (Km km1) (Km km2) = compare km1 km2
  compare (M m) (Km km)     = compare m (km * 1000)
  compare (Km km) (M m)     = compare (km * 1000) m

-- Main to demonstrate comparisons
main :: IO ()
main = do
  let len1 = M 500      -- 500 meters
  let len2 = Km 0.3     -- 0.3 kilometers = 300 meters
  let len3 = Km 1.0     -- 1 kilometer = 1000 meters
  let len4 = M 1000     -- 1000 meters

  putStrLn $ show len1 ++ " < " ++ show len2 ++ ": " ++ show (len1 < len2)  -- False
  putStrLn $ show len2 ++ " < " ++ show len1 ++ ": " ++ show (len2 < len1)  -- True
  putStrLn $ show len3 ++ " == " ++ show len4 ++ ": " ++ show (len3 == len4) -- False (Eq derived, so different constructors not equal)
  putStrLn $ show len3 ++ " > " ++ show len1 ++ ": " ++ show (len3 > len1)  -- True
  putStrLn $ show len4 ++ " == " ++ show (M 1000) ++ ": " ++ show (len4 == M 1000) -- True
```

---

### Explanation

* `Eq` is derived, so `M 1000 == Km 1.0` is `False` because constructors differ.
* `Ord` is implemented manually comparing meters and kilometers correctly by converting `Km` to meters.
* In `main`, you can see that ordering compares actual length values, but equality is strict on constructors.

---

### Sample Output

```
M 500.0 < Km 0.3: False
Km 0.3 < M 500.0: True
Km 1.0 == M 1000.0: False
Km 1.0 > M 500.0: True
M 1000.0 == M 1000.0: True
```

---

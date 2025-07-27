
* `Low`
* `Medium`
* `High`
* `Critical`

We'll make `Severity` an instance of `Semigroup` such that **combining two severity levels always returns the more severe one** (i.e., the maximum of the two).

---

## ✅ Code

```haskell
-- Define the Severity data type with four levels
data Severity = Low | Medium | High | Critical
  deriving (Show, Eq, Ord)

-- Make Severity an instance of Semigroup
instance Semigroup Severity where
  (<>) = max  -- Higher severity overrides the lower one

-- Optional: Make it a Monoid with Low as the identity
instance Monoid Severity where
  mempty = Low

main :: IO ()
main = do
  putStrLn "Demonstrating Severity combination:"
  
  let s1 = Medium
      s2 = High
      s3 = Low
      s4 = Critical
  
  putStrLn $ "Combining " ++ show s1 ++ " and " ++ show s2 ++ ": " ++ show (s1 <> s2)
  putStrLn $ "Combining " ++ show s2 ++ " and " ++ show s3 ++ ": " ++ show (s2 <> s3)
  putStrLn $ "Combining " ++ show s1 ++ " and " ++ show s4 ++ ": " ++ show (s1 <> s4)
  putStrLn $ "Combining " ++ show s3 ++ " and mempty: " ++ show (s3 <> mempty)
```

---

## 🔍 Explanation

### 🔹 `Severity` type:

* Uses `deriving (Show, Eq, Ord)`:

  * `Ord` allows comparison: `Low < Medium < High < Critical`.

### 🔹 `Semigroup` instance:

* Defines `(<>) = max` so that the **most severe** of the two values is returned.

### 🔹 `Monoid` instance (optional):

* Sets `mempty = Low` — combining with `Low` has no effect (identity).

### 🔹 `main`:

* Demonstrates different combinations of severities and prints results.

---


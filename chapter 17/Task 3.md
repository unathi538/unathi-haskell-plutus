
* Combining two `Severity` values returns the **more severe one** (i.e., `max`).
* The **identity value** for the `Monoid` is `Low`.

---

## ✅ Full Working Code

```haskell
-- Define the Severity data type
data Severity = Low | Medium | High | Critical
  deriving (Show, Eq, Ord)

-- Semigroup instance: combine by taking the higher severity
instance Semigroup Severity where
  (<>) = max

-- Monoid instance: identity is Low
instance Monoid Severity where
  mempty = Low

main :: IO ()
main = do
  putStrLn "Combining severities using Semigroup and Monoid instances:\n"

  let s1 = Medium
      s2 = High
      s3 = Low
      s4 = Critical

  -- Semigroup examples
  putStrLn $ show s1 ++ " <> " ++ show s2 ++ " = " ++ show (s1 <> s2)
  putStrLn $ show s3 ++ " <> " ++ show s4 ++ " = " ++ show (s3 <> s4)

  -- Monoid identity tests
  putStrLn $ show s1 ++ " <> mempty = " ++ show (s1 <> mempty)
  putStrLn $ "mempty <> " ++ show s4 ++ " = " ++ show (mempty <> s4)
```

---

## 🔍 Explanation

### 🔸 `Severity` Type

A simple `Enum`-like type with 4 severity levels, where:

```
Low < Medium < High < Critical
```

The `Ord` instance allows comparison using `max`.

### 🔸 Semigroup

```haskell
instance Semigroup Severity where
  (<>) = max
```

Combining two severities keeps the one with **higher priority**.

### 🔸 Monoid

```haskell
instance Monoid Severity where
  mempty = Low
```

Defines `Low` as the **neutral/identity** value, so:

```haskell
x <> mempty == x
```

### 🔸 main

Demonstrates combining values and using the identity `mempty`.

---


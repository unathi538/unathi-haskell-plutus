Absolutely! Let's implement a function called `nestedFmap` that applies a transformation function to a **nested functor** — for example, `Maybe [a]`, `Either e (Maybe a)`, or `IO (Maybe a)` — using multiple `fmap` calls.

---

### 🧠 Core Idea:

If you have a **nested functor** like `Maybe [Int]`, to apply a function like `(+1)` to the inner `Int`, you'd write:

```haskell
fmap (fmap (+1)) (Just [1, 2, 3])  -- Result: Just [2,3,4]
```

Each `fmap` peels away one layer of functor.

---

### ✅ Example with `Maybe [a]`

```haskell
-- nestedFmap applies a function to the inner values of a nested functor
nestedFmap :: (Functor f, Functor g) => (a -> b) -> f (g a) -> f (g b)
nestedFmap = fmap . fmap

main :: IO ()
main = do
  let val1 = Just [1, 2, 3]
  let val2 = Nothing :: Maybe [Int]

  putStrLn "Original nested values:"
  print val1
  print val2

  let result1 = nestedFmap (+1) val1
  let result2 = nestedFmap (+1) val2

  putStrLn "\nAfter applying nestedFmap (+1):"
  print result1
  print result2
```

---

### 📘 Explanation:

* `nestedFmap` is defined as `fmap . fmap`, which composes two `fmap`s.
* This lets you apply a function **inside two levels** of functors (e.g., `Maybe [a]`, `IO (Maybe a)`).
* In `main`, we demonstrate this with a `Maybe [Int]`.
* `Just [1, 2, 3]` becomes `Just [2, 3, 4]`.
* `Nothing` stays `Nothing` (nothing to map over).

---

### 🖥️ Sample Output:

```
Original nested values:
Just [1,2,3]
Nothing

After applying nestedFmap (+1):
Just [2,3,4]
Nothing
```

Would you like a version using `Either`, `IO`, or even `Tree (Maybe a)`?

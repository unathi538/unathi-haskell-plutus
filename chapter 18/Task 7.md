

---

### ✅ Full Working Example:

```haskell
-- fmapTuple applies a function to the second element of a tuple
fmapTuple :: (a -> b) -> (r, a) -> (r, b)
fmapTuple = fmap

main :: IO ()
main = do
  let pair1 = ("count", 10)
  let pair2 = ("total", 25)

  putStrLn "Original tuples:"
  print pair1
  print pair2

  let result1 = fmapTuple (+1) pair1
  let result2 = fmapTuple (*2) pair2

  putStrLn "\nAfter applying fmapTuple:"
  print result1
  print result2
```

---

### 🧠 Explanation:

* The type `(r, a)` is an instance of `Functor` **with respect to `a`**.
* `fmapTuple` is just `fmap`, specialized to tuples — it transforms the second value.
* `fmapTuple (+1) ("count", 10)` results in `("count", 11)`.

---


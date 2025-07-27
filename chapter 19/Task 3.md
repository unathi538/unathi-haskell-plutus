
## ✅ Goal:

We want a function:

```haskell
safeProduct :: [Maybe Int] -> Maybe Int
```

* If **all elements** in the list are `Just n`, it returns `Just (product of the n's)`.
* If **any element** is `Nothing`, it returns `Nothing`.

We can achieve this by converting the list of `Maybe Int` to a single `Maybe [Int]` using `sequence` (or `traverse id`), then computing the `product`.

---

### ✅ Full Working Code:

```haskell
-- safeProduct calculates the product of Maybe Ints, fails if any are Nothing
safeProduct :: [Maybe Int] -> Maybe Int
safeProduct xs = fmap product (sequence xs)
-- Alternatively: safeProduct xs = product <$> sequence xs

main :: IO ()
main = do
  let list1 = [Just 2, Just 3, Just 4]
  let list2 = [Just 5, Nothing, Just 6]
  let list3 = []

  putStrLn "Testing safeProduct:"
  print $ safeProduct list1  -- Just 24
  print $ safeProduct list2  -- Nothing
  print $ safeProduct list3  -- Just 1
```

---

### 🧠 Explanation:

* `sequence :: [Maybe a] -> Maybe [a]`:

  * If all values are `Just`, you get `Just [a]`.
  * If any is `Nothing`, you get `Nothing`.
* `fmap product` applies `product` to the unwrapped `[Int]` if the `Maybe` is not `Nothing`.

---

### 🖥️ Output:

```
Testing safeProduct:
Just 24
Nothing
Just 1
```

* ✅ `list1`: All values are `Just`, so product is `2*3*4 = 24`.
* ❌ `list2`: Contains a `Nothing`, so the result is `Nothing`.
* ✅ `list3`: Empty list — product of an empty list is `1`, so result is `Just 1`.


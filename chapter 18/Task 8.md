
```haskell
fmap id x == x
```

To **verify this law**, we can implement a function `identityLawCheck` that takes a functorial value (e.g. `Maybe`, `List`, `Tree`, etc.) and checks if applying `fmap id` returns the same value.

We'll use `Eq` to compare the original and the mapped value, and we'll also require `Show` to print the result in `main`.

---

### ✅ Full Working Example (using `Maybe` and `Tree`):

We’ll:

1. Define a binary `Tree` type with a `Functor` instance.
2. Implement `identityLawCheck`.
3. Demonstrate the law for `Maybe` and `Tree`.

```haskell
-- Define a simple binary Tree data type
data Tree a = Empty | Node a (Tree a) (Tree a)
  deriving (Eq, Show)

-- Functor instance for Tree
instance Functor Tree where
  fmap _ Empty = Empty
  fmap f (Node x l r) = Node (f x) (fmap f l) (fmap f r)

-- Function to check Functor identity law: fmap id x == x
identityLawCheck :: (Eq f, Functor t) => t f -> Bool
identityLawCheck x = fmap id x == x

main :: IO ()
main = do
  -- Test with Maybe
  let maybeVal1 = Just 42
  let maybeVal2 = Nothing

  putStrLn "Checking identity law for Maybe:"
  print $ identityLawCheck maybeVal1  -- Should be True
  print $ identityLawCheck maybeVal2  -- Should be True

  -- Test with Tree
  let treeVal = Node 1 (Node 2 Empty Empty) (Node 3 Empty Empty)

  putStrLn "\nChecking identity law for Tree:"
  print $ identityLawCheck treeVal  -- Should be True
```

---

### 🧠 Explanation:

* `identityLawCheck` checks if applying `fmap id` results in the original value.
* We use `(Eq f)` so we can compare the result.
* We test it on `Maybe` and a custom `Tree` type.
* Both should return `True` if the `Functor` instances are correct.

---

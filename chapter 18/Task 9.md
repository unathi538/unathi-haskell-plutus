
---

### 🧠 **Functor Composition Law**:

For any functor `F` and functions `f` and `g`:

```haskell
fmap (f . g) x == (fmap f . fmap g) x
```

This means mapping a composed function is the same as mapping one function, then the other.

---

### ✅ Complete Working Example (including `Tree` and `Maybe`):

We'll:

1. Use `Maybe` and a custom `Tree` functor.
2. Write `compositionLawCheck` to verify the law.
3. Test it in `main`.

```haskell
-- Define a binary Tree type
data Tree a = Empty | Node a (Tree a) (Tree a)
  deriving (Eq, Show)

-- Functor instance for Tree
instance Functor Tree where
  fmap _ Empty = Empty
  fmap f (Node x l r) = Node (f x) (fmap f l) (fmap f r)

-- Functor composition law: fmap (f . g) == fmap f . fmap g
compositionLawCheck :: (Eq (t c), Functor t) => (b -> c) -> (a -> b) -> t a -> Bool
compositionLawCheck f g x = fmap (f . g) x == (fmap f . fmap g) x

main :: IO ()
main = do
  -- Functions to use
  let f = (*2)
  let g = (+3)

  -- Maybe tests
  let maybeVal1 = Just 4
  let maybeVal2 = Nothing

  putStrLn "Checking composition law for Maybe:"
  print $ compositionLawCheck f g maybeVal1  -- True
  print $ compositionLawCheck f g maybeVal2  -- True

  -- Tree test
  let treeVal = Node 1 (Node 2 Empty Empty) (Node 3 Empty Empty)

  putStrLn "\nChecking composition law for Tree:"
  print $ compositionLawCheck f g treeVal    -- True
```

---

### 🧪 Explanation:

* `compositionLawCheck` takes:

  * Two functions `f :: b -> c` and `g :: a -> b`
  * A functorial value `x :: t a`
* It compares `fmap (f . g) x` with `(fmap f . fmap g) x`.
* Works for any functor like `Maybe`, `Tree`, `[]`, etc.

---


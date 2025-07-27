
```haskell
data Pair a = Pair a a
```

We'll:

1. Derive `Show` and `Eq` for testing.
2. Implement `Functor` (a requirement for `Applicative`).
3. Implement `Applicative` for `Pair`, where:

   * `pure x = Pair x x`
   * `(<*>) (Pair f1 f2) (Pair x1 x2) = Pair (f1 x1) (f2 x2)`
4. Show how to use it in `main`.

---

### ✅ Full Working Example:

```haskell
-- Define the Pair data type
data Pair a = Pair a a
  deriving (Show, Eq)

-- Functor instance for Pair
instance Functor Pair where
  fmap f (Pair x y) = Pair (f x) (f y)

-- Applicative instance for Pair
instance Applicative Pair where
  pure x = Pair x x
  (Pair f1 f2) <*> (Pair x1 x2) = Pair (f1 x1) (f2 x2)

-- Example usage
main :: IO ()
main = do
  let pair1 = Pair 1 2
  let pair2 = Pair 10 20

  putStrLn "Original Pairs:"
  print pair1
  print pair2

  -- Apply a Pair of functions to a Pair of values
  let funcPair = Pair (+1) (*2)
  let applied = funcPair <*> pair1

  putStrLn "\nApplying Pair of functions (+1, *2) to Pair (1, 2):"
  print applied

  -- Using pure to lift a value
  let lifted = pure 5 :: Pair Int
  putStrLn "\nUsing pure to create a Pair:"
  print lifted
```

---

### 📘 Explanation:

* `Functor` applies a function to both elements of a `Pair`.
* `Applicative`:

  * `pure x = Pair x x` puts the same value into both slots.
  * `(<*>)` applies each function to the corresponding element:
    `(Pair f1 f2) <*> (Pair x1 x2) = Pair (f1 x1) (f2 x2)`
* In `main`, we demonstrate applying a pair of functions to a pair of values and using `pure`.


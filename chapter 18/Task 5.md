

```haskell
data Either a b = Left a | Right b
```

The usual `Functor` instance applies `fmap` only to the `Right` value, leaving `Left` untouched.

Here’s a complete working example that defines a custom `MyEither` type with a `Functor` instance where `fmap` applies only to the `Right` case:

```haskell
-- Define a custom Either type
data MyEither a b = MyLeft a | MyRight b
  deriving (Show)

-- Functor instance for MyEither applies fmap to the Right value only
instance Functor (MyEither a) where
  fmap _ (MyLeft x)  = MyLeft x
  fmap f (MyRight y) = MyRight (f y)

-- Example usage
main :: IO ()
main = do
  let val1 = MyLeft "Error occurred"
  let val2 = MyRight 10

  putStrLn "Original values:"
  print val1
  print val2

  let mapped1 = fmap (+5) val1
  let mapped2 = fmap (+5) val2

  putStrLn "\nAfter fmap (+5):"
  print mapped1
  print mapped2
```

---

### Explanation:

* `MyEither` mimics the standard `Either` type.
* `Functor (MyEither a)` instance defines `fmap` such that:

  * If it's `MyLeft x`, return it unchanged.
  * If it's `MyRight y`, apply the function `f` to `y`.
* In `main`, you can see that mapping over a `MyLeft` value leaves it unchanged, while mapping over a `MyRight` value applies the function.

---


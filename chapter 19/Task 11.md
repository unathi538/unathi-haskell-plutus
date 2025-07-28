
---

### ✅ **HC11T1: `Applicative` instance for `Wrapper a`**

```haskell
data Wrapper a = Wrapper a deriving Show

instance Functor Wrapper where
  fmap f (Wrapper x) = Wrapper (f x)

instance Applicative Wrapper where
  pure = Wrapper
  (Wrapper f) <*> (Wrapper x) = Wrapper (f x)

main :: IO ()
main = do
  let a = Wrapper (*2)
      b = Wrapper 10
  print $ a <*> b  -- Wrapper 20
```

**Explanation:**

* `Wrapper` is a custom container.
* We define `fmap` and `<*>` for it, following applicative rules.

---


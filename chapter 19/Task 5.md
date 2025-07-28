 implement the function `applyEffects` that:

* Takes a tuple of two `IO Int` actions (e.g. `(IO Int, IO Int)`).
* Uses the `<*>` operator from the `Applicative` instance for `IO`.
* Sums the two values and prints them.

---

### ✅ Overview

* `(<*>) :: IO (a -> b) -> IO a -> IO b` — applies a function inside `IO` to an `IO` value.
* We'll use this to apply `(\x y -> x + y)` to two `IO Int` values.

---

### ✅ Full Working Example

```haskell
-- Define applyEffects using applicative style to sum two IO Ints
applyEffects :: (IO Int, IO Int) -> IO Int
applyEffects (io1, io2) = (\x y -> x + y) <$> io1 <*> io2

main :: IO ()
main = do
  -- Simulate two IO Int values (could be from input, random, etc.)
  let ioA = do
        putStrLn "Enter first number:"
        readLn :: IO Int

  let ioB = do
        putStrLn "Enter second number:"
        readLn :: IO Int

  putStrLn "Summing two IO Int values using applyEffects..."
  result <- applyEffects (ioA, ioB)
  putStrLn $ "The result is: " ++ show result
```

---

### 🧠 Explanation

* `(\x y -> x + y)` is a pure function we lift into the `IO` context using `<$>` and `<*>`.
* `applyEffects (io1, io2)` will:

  * Run the first `IO Int`, get `x`.
  * Run the second `IO Int`, get `y`.
  * Return `x + y` inside `IO`.

---


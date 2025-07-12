

* A type class `Summable` with a function `sumUp :: [a] -> a`.
* An instance of `Summable` for `Int`.
* A `main` function demonstrating usage.

```haskell
-- Define the Summable type class
class Summable a where
  sumUp :: [a] -> a

-- Implement Summable for Int
instance Summable Int where
  sumUp = sum

-- Main function to demonstrate
main :: IO ()
main = do
  let numbers = [1, 2, 3, 4, 5]
  putStrLn "Sum of numbers:"
  print (sumUp numbers)
```

---

### Explanation:

* `Summable` type class requires a `sumUp` function.
* For `Int`, `sumUp` uses the built-in `sum` function.
* `main` prints the sum of a list of integers.

---

### Sample output:

```
Sum of numbers:
15
```


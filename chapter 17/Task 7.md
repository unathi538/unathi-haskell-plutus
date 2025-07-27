

We'll define a function `multiplyProducts` that takes a list of `Product` values and combines them using `mconcat`.

---

## ✅ Full Working Code

```haskell
import Data.Monoid (Product(..), getProduct)

-- Multiply a list of Product-wrapped values using mconcat
multiplyProducts :: [Product Int] -> Product Int
multiplyProducts = mconcat

main :: IO ()
main = do
  let products1 = [Product 2, Product 3, Product 4]   -- 2 * 3 * 4 = 24
      products2 = [Product 5, Product 1, Product 1]   -- 5 * 1 * 1 = 5
      products3 = []                                 -- mconcat [] = mempty = Product 1

  putStrLn "Combining Product values using multiplyProducts:"
  putStrLn $ "Result 1: " ++ show (getProduct (multiplyProducts products1))
  putStrLn $ "Result 2: " ++ show (getProduct (multiplyProducts products2))
  putStrLn $ "Result 3 (empty list): " ++ show (getProduct (multiplyProducts products3))
```

---

## 🔍 Explanation

### 🔹 `Product` newtype

```haskell
newtype Product a = Product a
```

* Wraps a number.
* Has a `Monoid` instance where:

  * `(<>) = (*)`
  * `mempty = 1`

### 🔹 `multiplyProducts` function

```haskell
multiplyProducts = mconcat
```

* Uses `mconcat` to multiply all the `Product` values in a list.

### 🔹 `getProduct`

* Extracts the inner numeric value from `Product`.

### 🔹 `main`

* Demonstrates using `multiplyProducts` with:

  * A normal list of values.
  * A list with 1s (identity elements).
  * An empty list, which returns `Product 1` as expected from the `Monoid`.

---


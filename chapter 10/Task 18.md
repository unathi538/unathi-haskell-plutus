

* Defines a `PaymentMethod` data type,
* Derives `Eq` and `Ord` instances automatically,
* Tests comparisons in `main`.

---

### ✅ Full Working Example

```haskell
-- Define the PaymentMethod type with derived Eq and Ord
data PaymentMethod = Cash | CreditCard | PayPal
  deriving (Show, Eq, Ord)

-- Main function to test comparisons
main :: IO ()
main = do
  let pm1 = Cash
  let pm2 = CreditCard
  let pm3 = PayPal

  putStrLn $ "pm1 == pm2: " ++ show (pm1 == pm2)  -- False
  putStrLn $ "pm1 < pm2: "  ++ show (pm1 < pm2)   -- True (based on declaration order)
  putStrLn $ "pm3 > pm2: "  ++ show (pm3 > pm2)   -- True

  putStrLn $ "Comparing pm1 and pm3: " ++ show (compare pm1 pm3) -- LT
  putStrLn $ "Comparing pm3 and pm3: " ++ show (compare pm3 pm3) -- EQ
```

---

### Explanation

* Deriving `Eq` and `Ord` automatically provides equality and ordering based on the order of constructors.
* `Cash < CreditCard < PayPal` based on declaration order.
* `main` demonstrates equality and ordering comparisons.

---

### Sample Output

```
pm1 == pm2: False
pm1 < pm2: True
pm3 > pm2: True
Comparing pm1 and pm3: LT
Comparing pm3 and pm3: EQ
```



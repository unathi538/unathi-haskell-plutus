
* Defines the `ShowSimple` type class requiring `showSimple :: a -> String`.
* Defines a `PaymentMethod` data type.
* Implements a `ShowSimple` instance for `PaymentMethod`.
* Includes a `main` function demonstrating usage.

```haskell
-- Define the ShowSimple type class
class ShowSimple a where
  showSimple :: a -> String

-- Define the PaymentMethod data type
data PaymentMethod = Cash | CreditCard | PayPal deriving Show

-- Implement ShowSimple instance for PaymentMethod
instance ShowSimple PaymentMethod where
  showSimple Cash       = "Paid with cash"
  showSimple CreditCard = "Paid with credit card"
  showSimple PayPal     = "Paid with PayPal"

-- Main function to demonstrate
main :: IO ()
main = do
  let payment1 = Cash
  let payment2 = CreditCard
  let payment3 = PayPal

  putStrLn $ showSimple payment1
  putStrLn $ showSimple payment2
  putStrLn $ showSimple payment3
```

---

### Explanation:

* `ShowSimple` defines a custom simple string conversion function.
* `PaymentMethod` is a simple enum-like type.
* The `ShowSimple` instance returns a friendly string description.
* `main` prints out the descriptions for three payment methods.

---

### Sample output when run:

```
Paid with cash
Paid with credit card
Paid with PayPal
```


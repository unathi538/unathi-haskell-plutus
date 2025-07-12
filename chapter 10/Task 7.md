

* A **multi-parameter type class** `Convertible a b` with a method `convert :: a -> b`,
* A `PaymentMethod` data type,
* An instance of `Convertible` for converting `PaymentMethod` to `String`,
* A `main` function that demonstrates it.

---

### ✅ Full Working Example

```haskell
{-# LANGUAGE MultiParamTypeClasses #-}

-- Define the Convertible type class
class Convertible a b where
  convert :: a -> b

-- Define the PaymentMethod data type
data PaymentMethod = Cash | CreditCard | PayPal deriving Show

-- Implement Convertible instance: PaymentMethod -> String
instance Convertible PaymentMethod String where
  convert Cash       = "Cash"
  convert CreditCard = "Credit Card"
  convert PayPal     = "PayPal"

-- Main function to demonstrate usage
main :: IO ()
main = do
  let method1 = Cash
  let method2 = CreditCard
  let method3 = PayPal

  putStrLn "Converted Payment Methods to Strings:"
  putStrLn (convert method1)
  putStrLn (convert method2)
  putStrLn (convert method3)
```

---

### 🔍 Explanation

* `MultiParamTypeClasses` language extension is required because `Convertible` uses **two type parameters**: `a` and `b`.
* `convert :: a -> b` allows defining how to convert from one type to another.
* We implement `convert` for `PaymentMethod -> String`.
* `main` prints out converted strings.

---

### 💡 Sample Output

```
Converted Payment Methods to Strings:
Cash
Credit Card
PayPal
```



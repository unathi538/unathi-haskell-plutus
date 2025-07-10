

* A custom data type `PaymentMethod` with constructors `Cash`, `Card`, and `Cryptocurrency`.
* A custom data type `Person` that contains:

  * A `name` (String)
  * An `address` (as a tuple of `String` and `Int`)
  * A `paymentMethod` (of type `PaymentMethod`)
* A value `bob` who pays with `Cash`.

---

### ✅ Haskell Code Example

```haskell
-- Define the PaymentMethod data type
data PaymentMethod = Cash | Card | Cryptocurrency deriving (Show)

-- Define the Person data type
data Person = Person {
    name :: String,
    address :: (String, Int),  -- e.g., ("Main Street", 123)
    paymentMethod :: PaymentMethod
} deriving (Show)

-- Create a person named Bob who pays with cash
bob :: Person
bob = Person {
    name = "Bob",
    address = ("Main Street", 42),
    paymentMethod = Cash
}

-- Main function to display Bob's info
main :: IO ()
main = do
    putStrLn "Person Info:"
    putStrLn $ "Name: " ++ name bob
    putStrLn $ "Address: " ++ fst (address bob) ++ ", " ++ show (snd (address bob))
    putStrLn $ "Payment Method: " ++ show (paymentMethod bob)
```

---

### 🧠 Explanation:

* `PaymentMethod` is an **enumeration** type with three possible values.
* `Person` is a **record type** with named fields.
* `bob` is a value of type `Person` with sample data.

---

### 💡 Sample Output:

```
Person Info:
Name: Bob
Address: Main Street, 42
Payment Method: Cash
```


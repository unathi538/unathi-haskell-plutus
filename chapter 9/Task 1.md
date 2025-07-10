

* A **parametric type synonym** `Entity a` to represent an entity with an address and a value of any type `a`.
* An example showing how you can use `Entity` for a person (with `String`) and for a transaction value (with `Int`).
* A `main` function to print those entities.

---

### ✅ Haskell Code Example

```haskell
-- Type synonym for Address
type Address = String

-- Parametric type synonym for Entity
type Entity a = (Address, a)

-- Example entities
personEntity :: Entity String
personEntity = ("addr1qperson...", "Alice")

transactionEntity :: Entity Int
transactionEntity = ("addr1qtxn...", 5000)

-- Main function to print entities
main :: IO ()
main = do
    putStrLn "Entity Examples:"
    putStrLn $ "Person Entity: " ++ show personEntity
    putStrLn $ "Transaction Entity: " ++ show transactionEntity
```

---

### 🧠 Explanation:

* `type Entity a = (Address, a)` defines a type synonym for a tuple combining an `Address` with any value of type `a`.
* This allows you to represent various entities with different types of associated data, e.g., names, amounts, etc.

---

### 💡 Sample Output:

```
Entity Examples:
Person Entity: ("addr1qperson...","Alice")
Transaction Entity: ("addr1qtxn...",5000)
```




* Two **type synonyms**: `Address` for `String`, and `Value` for `Int`.
* A function `generateTx` that takes two addresses (sender and receiver) and a value, and returns a formatted transaction string.

---

### ✅ Haskell Code Example

```haskell
-- Type synonyms
type Address = String
type Value = Int

-- Function to generate a transaction string
generateTx :: Address -> Address -> Value -> String
generateTx from to amount =
    "Transaction from " ++ from ++ " to " ++ to ++ " of value " ++ show amount

-- Main function to test generateTx
main :: IO ()
main = do
    let sender = "addr1qxyz..."
    let receiver = "addr1qabc..."
    let valueSent = 1000

    putStrLn $ generateTx sender receiver valueSent
```

---

### 🧠 Explanation:

* `type Address = String` and `type Value = Int` make the code more **readable and domain-specific**.
* `generateTx` builds a human-readable transaction summary by concatenating strings and converting the integer value using `show`.

---

### 💡 Sample Output:

```
Transaction from addr1qxyz... to addr1qabc... of value 1000
```


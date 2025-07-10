

* Defines **type synonyms**:

  * `Address` for `String`
  * `Value` for `Int`
* Defines a **`Transaction`** type using **record syntax** with fields:

  * `from`, `to`, `amount`, and `transactionId`
* Implements `createTransaction :: Address -> Address -> Value -> String`, which:

  * Creates a transaction
  * Returns the transaction ID (which is auto-generated here using a simple counter or placeholder)

---

### ✅ Haskell Code Example

```haskell
import Data.Time.Clock.POSIX (getPOSIXTime)

-- Type synonyms
type Address = String
type Value   = Int

-- Define the Transaction type
data Transaction = Transaction
  { from          :: Address
  , to            :: Address
  , amount        :: Value
  , transactionId :: String
  } deriving (Show)

-- Function to create a Transaction and return the transaction ID
createTransaction :: Address -> Address -> Value -> IO String
createTransaction fromAddr toAddr val = do
    timestamp <- getPOSIXTime
    let txId = "tx-" ++ show (round (timestamp * 1000) :: Integer)
        tx = Transaction { from = fromAddr, to = toAddr, amount = val, transactionId = txId }
    putStrLn $ "Transaction created: " ++ show tx
    return txId

-- Main function to test createTransaction
main :: IO ()
main = do
    let sender   = "addr1qsender..."
    let receiver = "addr1qreceiver..."
    let value    = 2500

    txId <- createTransaction sender receiver value
    putStrLn $ "Transaction ID: " ++ txId
```

---

### 🧠 Explanation:

* `Transaction` is defined using **record syntax** for easy field access.
* `createTransaction` uses `getPOSIXTime` to simulate a unique transaction ID.
* The function **prints the full transaction** and returns the generated `transactionId`.

---

### 💡 Sample Output (will vary by time):

```
Transaction created: Transaction {from = "addr1qsender...", to = "addr1qreceiver...", amount = 2500, transactionId = "tx-1720610282732"}
Transaction ID: tx-1720610282732
```


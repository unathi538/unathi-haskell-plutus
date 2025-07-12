

* Defines a `WeAccept` type class with an `accept` method and a new `fancyFunction`,
* Creates types: `Cardano`, `Cash`, and `Country`,
* Implements `WeAccept` instances for each type,
* Implements `fancyFunction` using pattern matching and `accept`,
* Demonstrates everything in `main`.

---

### ✅ Full Working Example

```haskell
-- Define the WeAccept type class with accept and fancyFunction
class WeAccept a where
  accept :: a -> Bool
  fancyFunction :: a -> String
  fancyFunction x =
    if accept x
      then "✅ Accepted: " ++ show x
      else "❌ Rejected: " ++ show x

-- Define Cardano type
data Cardano = CardanoWallet String deriving Show

-- Define Cash type
data Cash = CashAmount Int deriving Show

-- Define Country type
data Country = CountryName String deriving Show

-- WeAccept instance for Cardano
instance WeAccept Cardano where
  accept (CardanoWallet name) = name /= "banned-wallet"

-- WeAccept instance for Cash
instance WeAccept Cash where
  accept (CashAmount amount) = amount > 0

-- WeAccept instance for Country
instance WeAccept Country where
  accept (CountryName name) = name `notElem` ["Noland", "Restricted"]

-- Main function to test fancyFunction
main :: IO ()
main = do
  -- Cardano tests
  let c1 = CardanoWallet "valid-wallet"
  let c2 = CardanoWallet "banned-wallet"

  -- Cash tests
  let money1 = CashAmount 100
  let money2 = CashAmount 0

  -- Country tests
  let country1 = CountryName "South Africa"
  let country2 = CountryName "Noland"

  putStrLn "Testing fancyFunction:\n"

  putStrLn $ fancyFunction c1
  putStrLn $ fancyFunction c2

  putStrLn $ fancyFunction money1
  putStrLn $ fancyFunction money2

  putStrLn $ fancyFunction country1
  putStrLn $ fancyFunction country2
```

---

### 🔍 Explanation

* `fancyFunction` uses the `accept` method to determine whether a value is acceptable and formats a string accordingly.
* Each custom type has its own `WeAccept` logic:

  * `CardanoWallet` is accepted unless it's `"banned-wallet"`.
  * `CashAmount` is accepted if it's greater than 0.
  * `CountryName` is accepted unless it’s `"Noland"` or `"Restricted"`.

---

### 💡 Sample Output

```
Testing fancyFunction:

✅ Accepted: CardanoWallet "valid-wallet"
❌ Rejected: CardanoWallet "banned-wallet"
✅ Accepted: CashAmount 100
❌ Rejected: CashAmount 0
✅ Accepted: CountryName "South Africa"
❌ Rejected: CountryName "Noland"
```

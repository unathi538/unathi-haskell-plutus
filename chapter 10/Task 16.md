

* Defines a type class `AdvancedEq` extending `Eq` with a new method `compareEquality :: a -> a -> Bool`,
* Defines a simple `Blockchain` type,
* Implements `Eq` and `AdvancedEq` for `Blockchain`,
* Demonstrates usage in `main`.

---

### ✅ Full Working Example

```haskell
-- Define Blockchain type
data Blockchain = Blockchain
  { blockHeight :: Int
  , chainId     :: String
  } deriving Show

-- Implement Eq for Blockchain
instance Eq Blockchain where
  (Blockchain h1 c1) == (Blockchain h2 c2) = h1 == h2 && c1 == c2

-- Define AdvancedEq type class extending Eq
class Eq a => AdvancedEq a where
  compareEquality :: a -> a -> Bool

-- Implement AdvancedEq for Blockchain
instance AdvancedEq Blockchain where
  -- For demonstration, we consider blocks equal if blockHeight matches, ignoring chainId
  compareEquality b1 b2 = blockHeight b1 == blockHeight b2

-- Main to demonstrate
main :: IO ()
main = do
  let chainA = Blockchain 100 "chain-1"
  let chainB = Blockchain 100 "chain-2"
  let chainC = Blockchain 101 "chain-1"

  putStrLn $ "chainA == chainB: " ++ show (chainA == chainB)             -- False (different chainId)
  putStrLn $ "chainA `compareEquality` chainB: " ++ show (compareEquality chainA chainB) -- True (same height)

  putStrLn $ "chainA == chainC: " ++ show (chainA == chainC)             -- False
  putStrLn $ "chainA `compareEquality` chainC: " ++ show (compareEquality chainA chainC) -- False
```

---

### Explanation

* `AdvancedEq` requires the type to be an instance of `Eq`.
* `compareEquality` provides a custom equality check, here based only on `blockHeight`.
* `==` checks both `blockHeight` and `chainId`.
* The demo shows how the two methods can differ.

---

### Sample Output

```
chainA == chainB: False
chainA `compareEquality` chainB: True
chainA == chainC: False
chainA `compareEquality` chainC: False
```





* Defines a type class `Comparable` with a function `compareWith :: a -> a -> Ordering`,
* Defines a `Blockchain` type (for demo, a simple wrapper with an `Int` representing block height),
* Implements `Comparable` for `Blockchain` based on block height,
* Includes a `main` function demonstrating usage.

```haskell
-- Define the Comparable type class
class Comparable a where
  compareWith :: a -> a -> Ordering

-- Define a simple Blockchain data type
data Blockchain = Blockchain
  { blockHeight :: Int
  } deriving Show

-- Implement Comparable for Blockchain
instance Comparable Blockchain where
  compareWith b1 b2 = compare (blockHeight b1) (blockHeight b2)

-- Main function to demonstrate
main :: IO ()
main = do
  let chain1 = Blockchain 10
  let chain2 = Blockchain 15

  putStrLn $ "Comparing chains: " ++ show chain1 ++ " and " ++ show chain2
  print $ compareWith chain1 chain2
```

---

### Explanation:

* `Comparable` is a custom class for comparing two values.
* `Blockchain` is a data type with an `Int` field `blockHeight`.
* `compareWith` compares `Blockchain`s by their height using built-in `compare`.
* `main` shows the comparison result (`LT`, `GT`, or `EQ`).

---

### Sample output:

```
Comparing chains: Blockchain {blockHeight = 10} and Blockchain {blockHeight = 15}
LT
```


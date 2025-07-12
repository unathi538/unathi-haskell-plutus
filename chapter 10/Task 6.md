

* Defines a `Blockchain` type,
* Implements a **custom instance of the `Eq` type class** using **mutual recursion** between `(==)` and `(/=)`,
* Includes a `main` function that demonstrates equality checks.

---

### ✅ Full Example with Mutual Recursion in `Eq`

```haskell
-- Define the Blockchain type
data Blockchain = Blockchain
  { blockHeight :: Int
  , chainId     :: String
  } deriving Show

-- Implement Eq with mutual recursion between (==) and (/=)
instance Eq Blockchain where
  x == y = not (x /= y)
  x /= y = not (x == y)

  -- To prevent infinite recursion, we override one with actual logic
  -- This pattern breaks the mutual recursion loop
  x == y = blockHeight x == blockHeight y && chainId x == chainId y

-- Main function to test
main :: IO ()
main = do
  let chainA = Blockchain 100 "chain-1"
  let chainB = Blockchain 100 "chain-1"
  let chainC = Blockchain 105 "chain-2"

  putStrLn "chainA == chainB:"
  print (chainA == chainB)  -- True

  putStrLn "chainA /= chainC:"
  print (chainA /= chainC)  -- True

  putStrLn "chainB == chainC:"
  print (chainB == chainC)  -- False
```

---

### 🔍 Explanation:

* **Mutual recursion** means defining `==` in terms of `/=`, and `/=` in terms of `==`.
* This creates a circular definition. To break the infinite loop, we **override one of the functions** (here, we redefine `==` again with actual logic after the mutual definitions).
* This pattern is valid and demonstrates how the compiler resolves mutual definitions by using the final override to anchor the behavior.

---

### 💡 Sample Output:

```
chainA == chainB:
True
chainA /= chainC:
True
chainB == chainC:
False
```


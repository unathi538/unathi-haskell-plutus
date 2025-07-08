HC2T3 - Task 3: Immutable Variables


---

### ✅ **Haskell Code Example**

```haskell
-- Define immutable variables with explicit types
myAge :: Int
myAge = 25

piValue :: Double
piValue = 3.14159

greeting :: String
greeting = "Hello, Haskell!"

isHaskellFun :: Bool
isHaskellFun = True

-- Main function to print the values
main :: IO ()
main = do
    putStrLn ("myAge (Int): " ++ show myAge)
    putStrLn ("piValue (Double): " ++ show piValue)
    putStrLn ("greeting (String): " ++ greeting)
    putStrLn ("isHaskellFun (Bool): " ++ show isHaskellFun)
```

---

### 🧪 How to Run

1. Save this code to a file called `ImmutableVars.hs`
2. In terminal or command prompt, compile and run:

```bash
ghc ImmutableVars.hs -o vars
./vars
```

---

### 🖨️ Example Output

```
myAge (Int): 25
piValue (Double): 3.14159
greeting (String): Hello, Haskell!
isHaskellFun (Bool): True
```


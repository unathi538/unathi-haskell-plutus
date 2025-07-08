HC2T1 - Task 1: Checking Types in GHCi

Since GHCi's `:type` (or `:t`) command is an interactive **REPL feature**, you can't use it directly inside a normal Haskell `main` function.



---

### ✅ **Working Haskell Example with `main`**

```haskell
main :: IO ()
main = do
    let intValue :: Int
        intValue = 42

    let floatValue :: Double
        floatValue = 3.14

    let stringValue :: String
        stringValue = "Haskell"

    let charValue :: Char
        charValue = 'Z'

    let boolValue :: Bool
        boolValue = True && False

    putStrLn ("The value of intValue (Int) is: " ++ show intValue)
    putStrLn ("The value of floatValue (Double) is: " ++ show floatValue)
    putStrLn ("The value of stringValue (String) is: " ++ show stringValue)
    putStrLn ("The value of charValue (Char) is: " ++ show charValue)
    putStrLn ("The value of boolValue (Bool) is: " ++ show boolValue)
```

---

### 🧪 How to Run

1. Save the code above in a file named `CheckTypes.hs`
2. Open a terminal and run:

```bash
ghc CheckTypes.hs -o checktypes
./checktypes
```

---

### 🖨️ Sample Output

```
The value of intValue (Int) is: 42
The value of floatValue (Double) is: 3.14
The value of stringValue (String) is: "Haskell"
The value of charValue (Char) is: 'Z'
The value of boolValue (Bool) is: False
```

This lets you **both run the code** and observe the **explicit types** of each expression within `main`.


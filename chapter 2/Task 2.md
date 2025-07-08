HC2T2 - Task 2: Function Type Signatures

Here is a **complete working Haskell program** that includes:

1. Function signatures
2. Function definitions
3. A `main` function to run and print the results

---

### ✅ **Haskell Code Example**

```haskell
-- Function signatures
add :: Int -> Int -> Int
isEven :: Int -> Bool
concatStrings :: String -> String -> String

-- Function definitions
add x y = x + y

isEven n = n `mod` 2 == 0

concatStrings s1 s2 = s1 ++ s2

-- Main function to test the above
main :: IO ()
main = do
    let sumResult = add 5 7
    putStrLn ("add 5 7 = " ++ show sumResult)

    let evenCheck = isEven 10
    putStrLn ("isEven 10 = " ++ show evenCheck)

    let stringResult = concatStrings "Hello, " "Haskell!"
    putStrLn ("concatStrings \"Hello, \" \"Haskell!\" = " ++ stringResult)
```

---

### 🧪 How to Run

1. Save the file as `FunctionsExample.hs`
2. Open terminal or command prompt and run:

```bash
ghc FunctionsExample.hs -o functions
./functions
```

---

### 🖨️ Sample Output

```
add 5 7 = 12
isEven 10 = True
concatStrings "Hello, " "Haskell!" = Hello, Haskell!
```



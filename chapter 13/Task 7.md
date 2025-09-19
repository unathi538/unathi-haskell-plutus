
HC13T7: Write a program that imports a function from your custom SumNonEmpty module and calculates the sum of a list of numbers. 

```haskell
-- Main.hs
-- Single-file version that simulates SumNonEmpty module

-- sumNonEmpty function
sumNonEmpty :: Num a => [a] -> a
sumNonEmpty [] = error "sumNonEmpty: cannot sum an empty list"
sumNonEmpty xs = sum xs

main :: IO ()
main = do
    putStrLn "Enter numbers separated by spaces:"
    line <- getLine
    let numbers = map read (words line) :: [Int]
    putStrLn ("The sum is: " ++ show (sumNonEmpty numbers))
```

---

## 🛠 How to Run

1. Open a terminal in the folder where you saved `Main.hs`.
2. Run without compiling:

```bash
runghc Main.hs
```

3. Or compile to an executable:

```bash
ghc Main.hs -o sumtest
./sumtest        # Linux/macOS
sumtest.exe      # Windows
```

---

### Example Run

```
Enter numbers separated by spaces:
5 10 20 15
The sum is: 50
```

If you enter nothing (empty list), it will crash with:

```
*** Exception: sumNonEmpty: cannot sum an empty list
```

---


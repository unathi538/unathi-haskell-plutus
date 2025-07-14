Here's a simple Haskell program that defines a module for mathematical operations and demonstrates its usage in the main function.

---

### Step 1: Create the module file `MathOps.hs`

```haskell
-- MathOps.hs
module MathOps (
    add,
    multiply,
    square,
    factorial
) where

-- Adds two numbers
add :: Num a => a -> a -> a
add x y = x + y

-- Multiplies two numbers
multiply :: Num a => a -> a -> a
multiply x y = x * y

-- Squares a number
square :: Num a => a -> a
square x = x * x

-- Calculates factorial of a number
factorial :: (Eq a, Num a, Ord a) => a -> a
factorial 0 = 1
factorial n
  | n > 0     = n * factorial (n - 1)
  | otherwise = error "Negative input not allowed"
```

---

### Step 2: Create the main file `Main.hs`

```haskell
-- Main.hs
import MathOps

main :: IO ()
main = do
    putStrLn $ "Add 5 and 7: " ++ show (add 5 7)
    putStrLn $ "Multiply 3 and 4: " ++ show (multiply 3 4)
    putStrLn $ "Square of 6: " ++ show (square 6)
    putStrLn $ "Factorial of 5: " ++ show (factorial 5)
```

---

### How to Run:

1. Save `MathOps.hs` and `Main.hs` in the same directory.
2. In the terminal, compile and run:

```bash
ghc Main.hs -o mainProgram
./mainProgram
```

Or run directly with:

```bash
runghc Main.hs
```

---

### Expected Output:

```
Add 5 and 7: 12
Multiply 3 and 4: 12
Square of 6: 36
Factorial of 5: 120
```



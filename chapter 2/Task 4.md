HC2T4 - Task 4: Converting Between Infix and Prefix Notations 



## ✅ Full Code with Explanation

```haskell
-- Prefix notation equivalents of infix expressions

prefixAdd :: Int
prefixAdd = (+) 5 3
-- Explanation: This is prefix notation.
-- The function (+) is applied to the values 5 and 3.
-- Equivalent to writing: 5 + 3
-- Result: 8

prefixMultiply :: Int
prefixMultiply = (*) 10 4
-- Explanation: (*) is the multiplication function.
-- This means: 10 * 4
-- Result: 40

prefixAnd :: Bool
prefixAnd = (&&) True False
-- Explanation: (&&) is the logical AND operator in prefix.
-- This means: True && False
-- Result: False (since one operand is False)
```

---

```haskell
-- Infix notation equivalents of prefix functions

infixAdd :: Int
infixAdd = 7 + 2
-- Explanation: Normal infix notation for addition.
-- Equivalent to writing: (+) 7 2
-- Result: 9

infixMultiply :: Int
infixMultiply = 6 * 5
-- Explanation: Normal multiplication with infix.
-- Equivalent to: (*) 6 5
-- Result: 30

infixAnd :: Bool
infixAnd = True && False
-- Explanation: Logical AND in infix form.
-- Equivalent to: (&&) True False
-- Result: False
```

---

```haskell
-- Main function to print results
main :: IO ()
main = do
    putStrLn "Prefix Notation Results:"
    putStrLn $ "(+) 5 3 = " ++ show prefixAdd
    putStrLn $ "(*) 10 4 = " ++ show prefixMultiply
    putStrLn $ "(&&) True False = " ++ show prefixAnd

    putStrLn "\nInfix Notation Results:"
    putStrLn $ "7 + 2 = " ++ show infixAdd
    putStrLn $ "6 * 5 = " ++ show infixMultiply
    putStrLn $ "True && False = " ++ show infixAnd
```

### 🔍 What this does:

* `putStrLn` prints text.
* `show` converts values (like `Int` and `Bool`) to strings so they can be printed.
* Each line shows the result of one expression, either in **prefix** or **infix** form.

---

## 💡 Summary of Concepts

| Concept            | Infix Notation   | Prefix Notation            |
| ------------------ | ---------------- | -------------------------- |
| Arithmetic (+, \*) | `a + b`, `a * b` | ` (+) a b`, ` (*) a b`     |
| Boolean AND (&&)   | `a && b`         | ` (&&) a b`                |
| Usage in Haskell   | Default is infix | Use parentheses for prefix |

---


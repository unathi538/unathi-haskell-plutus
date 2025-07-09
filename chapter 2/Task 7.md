HC2T7 - Task 7: Boolean Expressions

Here's a complete and working **Haskell code example** that includes:

1. A Boolean expression that evaluates to **`True` using `&&`** (logical AND).
2. A Boolean expression that evaluates to **`False` using `||`** (logical OR).
3. A Boolean expression that evaluates to **`True` using `not`**.
4. A **comparison expression** that evaluates to **`False`**.

Each expression is tested and printed in the `main` function.

---

### ✅ Haskell Code

```haskell
-- Boolean expression using &&
trueUsingAnd :: Bool
trueUsingAnd = True && True
-- Both operands are True → result is True

-- Boolean expression using ||
falseUsingOr :: Bool
falseUsingOr = False || False
-- Both operands are False → result is False

-- Boolean expression using not
trueUsingNot :: Bool
trueUsingNot = not False
-- not False → True

-- Comparison that returns False
falseComparison :: Bool
falseComparison = 5 > 10
-- 5 is not greater than 10 → False

-- Main function to print all results
main :: IO ()
main = do
    putStrLn "Boolean Expressions Results:"
    putStrLn $ "True && True = " ++ show trueUsingAnd
    putStrLn $ "False || False = " ++ show falseUsingOr
    putStrLn $ "not False = " ++ show trueUsingNot
    putStrLn $ "5 > 10 = " ++ show falseComparison
```

---






### 🔍 Explanation:

* `>` is a comparison operator for "greater than."
* `5 > 10` is `False` because 5 is **not** greater than 10.
* Other comparison operators you can use include: `<`, `==`, `/=`, `<=`, `>=`.

---

```haskell
-- Main function to print all results
main :: IO ()
main = do
    putStrLn "Boolean Expressions Results:"
    putStrLn $ "True && True = " ++ show trueUsingAnd
    putStrLn $ "False || False = " ++ show falseUsingOr
    putStrLn $ "not False = " ++ show trueUsingNot
    putStrLn $ "5 > 10 = " ++ show falseComparison
```

### 🔍 Explanation:

* The `main` function is where the program starts.
* `putStrLn` is used to print strings.
* `show` converts Boolean values (`True`, `False`) into strings so they can be printed.
* Each expression result is shown with a label for clarity.

---


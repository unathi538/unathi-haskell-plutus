Absolutely! Here's the **Haskell program** again, followed by a **detailed explanation** of each part.

---

### ✅ Haskell Code:

```haskell
-- Define a function that takes two integers and returns their sum
addNumbers :: Int -> Int -> Int
addNumbers x y = x + y

-- Main function to run the program
main :: IO ()
main = do
    putStrLn "Enter the first number:"
    input1 <- getLine
    putStrLn "Enter the second number:"
    input2 <- getLine
    let num1 = read input1 :: Int
    let num2 = read input2 :: Int
    let result = addNumbers num1 num2
    putStrLn $ "The sum is: " ++ show result
```

---

### 🧠 Explanation:

#### 🔹 Function Definition: `addNumbers`

```haskell
addNumbers :: Int -> Int -> Int
addNumbers x y = x + y
```

* This line defines a function named `addNumbers`.
* It takes **two arguments**, both of type `Int` (i.e., integers).
* It returns the **sum** of `x` and `y` using the `+` operator.

#### 🔹 The `main` function:

The `main` function is the entry point of any Haskell program that does I/O (input/output). Here's a breakdown of what it does:

---




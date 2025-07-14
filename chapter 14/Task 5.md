

* A **custom data type**: `Result a`
* **Pattern matching** with the `@` symbol (also called **as-patterns**), which lets you refer to the whole value while also deconstructing it.

---

## ✅ Step-by-Step Working Example

### 📄 1. Code: `Main.hs`

```haskell
module Main where

-- Define a custom data type
data Result a = Success a | Error String
  deriving Show

-- Function that demonstrates pattern matching using @ (as-pattern)
describeResult :: Show a => Result a -> String
describeResult r@(Success val) =
  "Matched: " ++ show r ++ " with value: " ++ show val
describeResult r@(Error msg) =
  "Matched: " ++ show r ++ " with error: " ++ msg

main :: IO ()
main = do
  let res1 = Success 42
      res2 = Error "Something went wrong"
  putStrLn $ describeResult res1
  putStrLn $ describeResult res2
```

---

## 🔍 Explanation

### ✅ Custom Data Type:

```haskell
data Result a = Success a | Error String
```

* It's a generic type similar to `Either` or `Maybe`, with two constructors:

  * `Success a` holds a successful value.
  * `Error String` holds an error message.

### ✅ Pattern Matching with `@`:

```haskell
r@(Success val)
```

* This says: **bind the whole value to `r`**, and **also extract `val`** from `Success`.
* Now you can use both the full original (`r`) and its parts (`val`) in the same expression.

---

## ✅ Output When Run

```bash
Matched: Success 42 with value: 42
Matched: Error "Something went wrong" with error: Something went wrong
```

---

This pattern is especially useful for logging, error reporting, or tracing where both the full input and its components are needed.



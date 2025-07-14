

## ✅ What is `TypeApplications`?

In Haskell, `read` is **polymorphic**:

```haskell
read :: Read a => String -> a
```

That means you must tell it *what type* to read into. With `TypeApplications`, you can do this explicitly like:

```haskell
read @Int "123"
```

---

## ✅ Step-by-Step Working Example

### 📄 1. Enable the Extension and Write the Code

Update your `app/Main.hs` to the following:

```haskell
{-# LANGUAGE TypeApplications #-}

module Main where

import Text.Read (readMaybe)

-- Function to convert string to Int using read with type application
convertStringToInt :: String -> Maybe Int
convertStringToInt s = readMaybe @Int s

main :: IO ()
main = do
  putStrLn "Enter a number:"
  input <- getLine
  case convertStringToInt input of
    Just n  -> putStrLn $ "You entered the number: " ++ show n
    Nothing -> putStrLn "Invalid number format!"
```

---

### 🔍 Explanation

* `{-# LANGUAGE TypeApplications #-}` enables the language extension.
* `readMaybe @Int s` uses **type application** to tell `readMaybe` to parse into an `Int`.
* We use `readMaybe` (from `Text.Read`) for **safe parsing** — it returns `Nothing` on invalid input.
* The user is prompted to enter a number, and the program either:

  * Prints the number back, or
  * Prints an error message.

---

## ✅ Step 2: Add `readMaybe` Dependency

If not already present, ensure your `.cabal` file includes:

```cabal
build-depends: base >=4.7 && <5
```

> You don’t need to add anything extra for `Text.Read`, as it’s part of `base`.

---

## ✅ Step 3: Build and Run

```bash
cabal build
cabal run
```

**Example Run:**

```
Enter a number:
42
You entered the number: 42
```

Or with invalid input:

```
Enter a number:
hello
Invalid number format!
```

---



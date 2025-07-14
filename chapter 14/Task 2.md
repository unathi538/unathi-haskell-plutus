

* Add the `random` package as a dependency.
* Update the `Main.hs` file to print a **random number between 1 and 100**.

---

## ✅ Step 1: Modify the `.cabal` File

In your `hello-cabal.cabal` file, locate the `build-depends` section under the `executable` section. Modify it like this:

```cabal
executable hello-cabal
  main-is:             Main.hs
  hs-source-dirs:      app
  build-depends:       base >=4.7 && <5,
                       random >=1.2
  default-language:    Haskell2010
```

> 📌 This adds a dependency on the `random` library.

---

## ✅ Step 2: Update `Main.hs`

Replace the content of `app/Main.hs` with the following code:

```haskell
-- app/Main.hs
module Main where

import System.Random (randomRIO)

main :: IO ()
main = do
  putStrLn "Generating a random number between 1 and 100..."
  num <- randomRIO (1, 100) :: IO Int
  putStrLn $ "Your random number is: " ++ show num
```

### 🔍 Explanation:

* `randomRIO (1, 100)` generates a random number in the inclusive range \[1, 100].
* `:: IO Int` specifies the type of the random number.
* `putStrLn` outputs the results to the terminal.

---

## ✅ Step 3: Build the Project

Run:

```bash
cabal build
```

---

## ✅ Step 4: Run the Executable

Run the program:

```bash
cabal run
```

**Sample Output:**

```
Generating a random number between 1 and 100...
Your random number is: 42
```

---

## ✅ Summary

* You added the `random` package in your `.cabal` file.
* You used `randomRIO` to generate a random number.
* The program compiles and runs with Cabal.


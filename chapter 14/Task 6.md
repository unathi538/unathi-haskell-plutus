

* `app/` for your **main executable**
* `src/` for your **library modules**

We’ll walk through setup, structure, and working code that compiles and runs.

---

## ✅ Step 1: Initialize the Project

Open a terminal and run:

```bash
cabal init --non-interactive --minimal --package-name my-project --exe
```

Then rename and restructure the folders:

```bash
mv my-project/src my-project/app          # move default src to app
mkdir my-project/src                      # create src for modules
```

---

## ✅ Final Directory Structure

```
my-project/
├── app/
│   └── Main.hs             -- Main executable
├── src/
│   └── MyModule.hs         -- Additional modules
├── my-project.cabal
├── Setup.hs
├── LICENSE
├── README.md
└── CHANGELOG.md
```

---

## ✅ Step 2: Edit `my-project.cabal`

Update the `executable` section to include both `app` and `src` as source directories:

```cabal
executable my-project
  main-is:             Main.hs
  hs-source-dirs:      app, src
  build-depends:       base >=4.7 && <5
  default-language:    Haskell2010
```

---

## ✅ Step 3: Create `src/MyModule.hs`

```haskell
-- src/MyModule.hs
module MyModule (greet) where

greet :: String -> String
greet name = "Hello, " ++ name ++ "!"
```

This defines a simple function `greet` in its own module.

---

## ✅ Step 4: Create `app/Main.hs`

```haskell
-- app/Main.hs
module Main where

import MyModule (greet)

main :: IO ()
main = do
  putStrLn (greet "Cabal Project Structure")
```

This imports and uses the `greet` function from `MyModule`.

---

## ✅ Step 5: Build and Run

```bash
cabal build
cabal run
```

### Output:

```
Hello, Cabal Project Structure!
```

---

## ✅ Summary

* `src/` holds reusable modules.
* `app/` holds the main application entry point (`Main.hs`).
* The `.cabal` file is configured to look in both folders.



To support **both a library and a main executable** in your Cabal project, you need to:

1. Define a `library` section in your `.cabal` file.
2. Keep reusable code (modules) in the `src/` directory for the library.
3. Define an `executable` that depends on the library and lives in `app/`.

---

## ✅ Example: Full Setup

### 🔧 1. Directory Structure

```
my-project/
├── app/
│   └── Main.hs         -- main executable
├── src/
│   └── MyModule.hs     -- library module
├── my-project.cabal
├── Setup.hs
└── other standard files...
```

---

### 📄 2. Edit `my-project.cabal`

Modify your `.cabal` file to include **both a library and an executable**:

```cabal
cabal-version:       >=1.10
name:                my-project
version:             0.1.0.0
build-type:          Simple

library
  exposed-modules:     MyModule
  hs-source-dirs:      src
  build-depends:       base >=4.7 && <5
  default-language:    Haskell2010

executable my-project
  main-is:             Main.hs
  hs-source-dirs:      app
  build-depends:       base >=4.7 && <5,
                       my-project
  default-language:    Haskell2010
```

> ✅ Note: `my-project` is listed as a dependency for the executable to use the library component.

---

### 📄 3. Create `src/MyModule.hs`

```haskell
-- src/MyModule.hs
module MyModule (greet) where

greet :: String -> String
greet name = "Hello, " ++ name ++ "!"
```

This is your library module, exposed by the `library` component.

---

### 📄 4. Create `app/Main.hs`

```haskell
-- app/Main.hs
module Main where

import MyModule (greet)

main :: IO ()
main = putStrLn (greet "Library + Executable")
```

This is your main program, using the `greet` function from the library.

---

## ✅ Build and Run

From the root directory, run:

```bash
cabal build
cabal run my-project
```

### ✅ Output:

```
Hello, Library + Executable!
```

---


To create a simple Haskell project using `cabal`, follow these steps. The project will output:
**`Hello, Cabal!`**

---

### ✅ Step-by-Step Instructions

#### 1. **Initialize the Cabal project**

Open a terminal and run:

```bash
cabal init --non-interactive --minimal --package-name hello-cabal --exe
```

This creates a minimal project named `hello-cabal` with a basic executable.

#### 2. **Project Structure**

After running the above command, the directory will look like this:

```
hello-cabal/
├── app/
│   └── Main.hs
├── hello-cabal.cabal
├── CHANGELOG.md
├── LICENSE
├── README.md
└── Setup.hs
```

#### 3. **Edit `app/Main.hs`**

Replace its contents with:

```haskell
-- app/Main.hs
module Main where

main :: IO ()
main = putStrLn "Hello, Cabal!"
```

This defines a `main` function that outputs the string using `putStrLn`.

---

### 4. **Build the Project**

In the project root, run:

```bash
cabal build
```

This compiles your executable.

---

### 5. **Run the Program**

After building, run the executable with:

```bash
cabal run
```

Output:

```
Hello, Cabal!
```

---

### ✅ Summary

* You used `cabal init` to scaffold the project.
* You edited `Main.hs` to include a `main` function.
* You built and ran the program with Cabal.


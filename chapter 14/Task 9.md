The `PartialTypeSignatures` extension in Haskell allows you to **use wildcards (`_`) in type signatures**, letting the compiler infer that part of the type.

This is useful for:

* Prototyping functions
* Letting GHC fill in details you're not ready to specify

---

## ✅ Working Code Example Using `PartialTypeSignatures`

### 📄 `app/Main.hs`

```haskell
{-# LANGUAGE PartialTypeSignatures #-}

module Main where

import Data.Char (toUpper)

-- Function with partial type signature
shout :: _ -> _
shout str = map toUpper str

main :: IO ()
main = do
  putStrLn "Enter text:"
  input <- getLine
  putStrLn $ "Shouted: " ++ shout input
```

---

### 🔍 Explanation

* `{-# LANGUAGE PartialTypeSignatures #-}` enables the extension.
* The function `shout` has type signature `shout :: _ -> _`:

  * GHC will infer it as `String -> String` because of `map toUpper`.
* If you leave `-Wpartial-type-signatures` on (it's on by default), GHC will show a **warning** unless you use an underscore **with a trailing underscore** like `_`.

You can also be more precise, e.g.:

```haskell
shout :: [Char] -> _
```

---

## ✅ Build and Run

Make sure your `.cabal` file includes the necessary extension:

```cabal
  ghc-options: -fno-warn-partial-type-signatures
```

Then:

```bash
cabal build
cabal run
```

### Example Input/Output:

```
Enter text:
hello there
Shouted: HELLO THERE
```

---

## ✅ Summary

* `PartialTypeSignatures` lets you write `_` in function type signatures.
* GHC fills in the blanks — useful during development or when writing generic functions.
* Combine with `-fno-warn-partial-type-signatures` to suppress warnings.


Here's how to implement a Haskell function `counts` that computes **character frequencies** in a given string and returns a list of **tuples** `(Char, Int)`.

---

## ✅ Full Working Code Example

```haskell
-- app/Main.hs
module Main where

import Data.List (group, sort)

-- | Count character frequency in a string.
counts :: String -> [(Char, Int)]
counts str = map (\g -> (head g, length g)) . group . sort $ str

main :: IO ()
main = do
  putStrLn "Enter a string:"
  input <- getLine
  let freq = counts input
  putStrLn "Character frequencies:"
  print freq
```

---

## 🔍 Explanation

### `counts :: String -> [(Char, Int)]`

* `sort str`: sorts the characters alphabetically.
* `group`: groups equal adjacent elements into sublists.

  * E.g. `"aabb"` → `["aa", "bb"]`
* `map (\g -> (head g, length g))`: turns each group into a tuple of character and count.

### Example:

Input:

```
banana
```

Output:

```haskell
[('a',3),('b',1),('n',2)]
```

---

## ✅ Build and Run

1. Save to `app/Main.hs`
2. If needed, set your `.cabal` file to include:

```cabal
  hs-source-dirs: app
  build-depends: base >=4.7 && <5
```

3. Then run:

```bash
cabal build
cabal run
```

---




## ✅ Working Example with Explanation

### 📄 Step 1: `Main.hs` with `NumericUnderscores`

```haskell
{-# LANGUAGE NumericUnderscores #-}

module Main where

main :: IO ()
main = do
  let million      = 1_000_000
      billion      = 1_000_000_000
      hexNumber    = 0xDEAD_BEEF
      binaryLike   = 0b1010_1100_0011  -- GHC doesn't support binary literals yet; this is just for show

  putStrLn $ "Million: " ++ show million
  putStrLn $ "Billion: " ++ show billion
  putStrLn $ "Hex number (DEADBEEF): " ++ show hexNumber
  putStrLn $ "Fake binary-like number: " ++ show binaryLike
```

---

### 🔍 Explanation

* `{-# LANGUAGE NumericUnderscores #-}` at the top enables the extension.
* Numeric literals like `1_000_000` are parsed exactly the same as `1000000`.
* `0xDEAD_BEEF` is a hexadecimal literal using underscores — valid with this extension.
* `0b1010_1100_0011` is *not* valid binary syntax in GHC (as of now), but you can still write numbers with underscores that resemble binary patterns for readability.

---


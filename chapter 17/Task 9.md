Got it! Let's define a `Config` data type with fields:

* `loggingLevel :: Int` (higher means more verbose)
* `timeout :: Int` (lower means faster timeout)
* `retries :: Int`

Then, implement a `Semigroup` instance that:

* Takes the **maximum** of `loggingLevel` and `retries` (to keep the "strongest" settings)
* Takes the **minimum** of `timeout` (to choose the fastest timeout)

---

## ✅ Full Working Code

```haskell
-- Define the Config data type
data Config = Config
  { loggingLevel :: Int  -- e.g., 0 (none) to 5 (verbose)
  , timeout      :: Int  -- timeout in seconds
  , retries      :: Int  -- number of retries
  } deriving (Show, Eq)

-- Semigroup instance combining Config values as described
instance Semigroup Config where
  Config l1 t1 r1 <> Config l2 t2 r2 =
    Config
      { loggingLevel = max l1 l2
      , timeout      = min t1 t2
      , retries      = max r1 r2
      }

main :: IO ()
main = do
  let cfg1 = Config { loggingLevel = 2, timeout = 30, retries = 3 }
      cfg2 = Config { loggingLevel = 4, timeout = 20, retries = 1 }
      combined = cfg1 <> cfg2

  putStrLn "Config 1:"
  print cfg1

  putStrLn "Config 2:"
  print cfg2

  putStrLn "Combined Config (using Semigroup <>):"
  print combined
```

---

## 🔍 Explanation

* The `Config` type holds three fields.
* The `Semigroup` instance combines two configs by:

  * Taking the **maximum** of `loggingLevel` (to be more verbose)
  * Taking the **minimum** of `timeout` (to respect the faster timeout)
  * Taking the **maximum** of `retries` (to allow more retry attempts)
* The `main` function shows combining two example configurations.

---

 

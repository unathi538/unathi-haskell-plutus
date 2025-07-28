

### ✅ **Code: `repeatEffect` using `forever`**

```haskell
import Control.Monad (forever)

-- | repeatEffect takes an IO action and repeats it infinitely using `forever`.
repeatEffect :: IO () -> IO ()
repeatEffect = forever

main :: IO ()
main = do
    putStrLn "Starting repeated effect. Press Ctrl+C to stop."
    repeatEffect $ putStrLn "Hello, Haskell!"
```

---

### 🧠 **Explanation**

* `forever` is a function from `Control.Monad` with type:

  ```haskell
  forever :: Monad m => m a -> m b
  ```

  It repeats a given monadic action endlessly.

* `repeatEffect` takes an `IO ()` (a side-effecting action that returns nothing) and uses `forever` to repeat it endlessly.

* In the `main` function, we:

  * Print an initial message.
  * Call `repeatEffect` with `putStrLn "Hello, Haskell!"` — this message will be printed again and again until you manually stop the program (usually with `Ctrl+C`).

---

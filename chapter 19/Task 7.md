
### ✅ **HC19T7: `conditionalPrint` using `when`**

```haskell
import Control.Monad (when)

conditionalPrint :: Bool -> IO ()
conditionalPrint condition = when condition $ putStrLn "Condition is True!"

main :: IO ()
main = do
  putStrLn "Running conditionalPrint with True:"
  conditionalPrint True
  putStrLn "Running conditionalPrint with False:"
  conditionalPrint False
```

**Explanation:**

* `when` is from `Control.Monad`. It executes the second argument only if the first is `True`.





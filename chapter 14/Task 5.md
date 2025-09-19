HC14T5: Write a Haskell program that uses a custom data type Result a and demonstrate pattern matching using the @ symbol. 

## ✅ Haskell Program:

```haskell
-- Enable strict warnings
{-# OPTIONS_GHC -Wall #-}

-- Define a custom data type
data Result a = Success a | Failure String
    deriving Show

-- Function that demonstrates pattern matching with @
describeResult :: Result Int -> String
describeResult r@(Success value) =
    "Got a Success with value " ++ show value ++ ", full result: " ++ show r
describeResult (Failure msg) =
    "Operation failed with message: " ++ msg

main :: IO ()
main = do
    let r1 = Success 42
        r2 = Failure "Something went wrong"

    putStrLn $ describeResult r1
    putStrLn $ describeResult r2
```

---


## 🔍 Explanation

### ✅ Custom Data Type:

```haskell
data Result a = Success a | Error String
```

* It's a generic type similar to `Either` or `Maybe`, with two constructors:

  * `Success a` holds a successful value.
  * `Error String` holds an error message.


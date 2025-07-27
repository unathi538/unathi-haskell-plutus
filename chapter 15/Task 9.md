

### ✅ **Working Example: File Reading with Exception Handling via `try`**

```haskell
-- FileReadTry.hs
module Main where

import System.IO
import Control.Exception
import System.IO.Error (ioeGetErrorString)

-- Main function that tries to read a file and catches exceptions
main :: IO ()
main = do
    putStrLn "Enter the filename to read:"
    fileName <- getLine
    result <- try (readFile fileName) :: IO (Either IOException String)
    case result of
        Right contents -> do
            putStrLn "\n--- File Contents ---"
            putStrLn contents
        Left e -> do
            putStrLn $ "An error occurred: " ++ ioeGetErrorString e
```

---



### 🧠 Example Output

**When the file exists:**

```
Enter the filename to read:
example.txt

--- File Contents ---
This is a test file.
```

**When the file doesn’t exist:**

```
Enter the filename to read:
missing.txt
An error occurred: missing.txt: openFile: does not exist (No such file or directory)
```

---

### 📘 Explanation

* `try :: Exception e => IO a -> IO (Either e a)` runs an I/O action and returns the result wrapped in `Right`, or the exception wrapped in `Left`.
* We explicitly tell the compiler we are catching `IOException`s using the type annotation:

  ```haskell
  result <- try (readFile fileName) :: IO (Either IOException String)
  ```
* `ioeGetErrorString` extracts a human-readable message from an `IOException`.




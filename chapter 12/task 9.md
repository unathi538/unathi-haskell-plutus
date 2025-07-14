Here's a complete Haskell program that reads a file and prints its contents to the terminal. It also gracefully handles the case where the file does not exist using `catch` from `Control.Exception`.

```haskell
-- ReadFile.hs

import System.IO
import Control.Exception

-- Main function to read a file and print its contents
main :: IO ()
main = do
    putStrLn "Enter the filename to read:"
    filename <- getLine
    -- Try reading the file, handle exceptions if the file doesn't exist
    result <- try (readFile filename) :: IO (Either IOError String)
    case result of
        Left err -> putStrLn ("Error: Could not read the file. " ++ show err)
        Right content -> do
            putStrLn "\nFile content:"
            putStrLn content
```

---

### ✅ How to Run:

1. Save this as `ReadFile.hs`.
2. Make sure you have a text file (e.g., `example.txt`) in the same directory.
3. Run the program:

```bash
runghc ReadFile.hs
```

---

### 💡 Example:

**Input:**

```
Enter the filename to read:
example.txt
```

**Output (if file exists):**

```
File content:
This is a test file.
Hello, world!
```

**Output (if file doesn't exist):**

```
Error: Could not read the file. ReadFile.hs: example.txt: openFile: does not exist (No such file or directory)
```


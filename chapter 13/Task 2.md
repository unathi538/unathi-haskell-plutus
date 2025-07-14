
```haskell
import System.Directory (listDirectory, doesFileExist)
import Data.List (isInfixOf)
import Control.Monad (filterM)

-- | Filters files in the current directory whose names contain the given substring.
filterFilesBySubstring :: String -> IO [FilePath]
filterFilesBySubstring substr = do
    entries <- listDirectory "."
    files <- filterM doesFileExist entries
    let filteredFiles = filter (substr `isInfixOf`) files
    return filteredFiles

main :: IO ()
main = do
    putStrLn "Enter substring to filter files:"
    substr <- getLine
    matchingFiles <- filterFilesBySubstring substr
    putStrLn "Matching files:"
    mapM_ putStrLn matchingFiles
```

---

### Explanation:

* **`listDirectory "."`**: Lists all entries (files and directories) in the current directory.
* **`filterM doesFileExist entries`**: Filters to keep only files.
* **`filter (substr \`isInfixOf\`) files\`**: Keeps only files where the filename contains the substring.
* The user is prompted to enter a substring, then matching filenames are printed.



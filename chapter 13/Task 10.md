 Here's a Haskell program that uses **`System.Directory`** to list files in the current directory and **`Data.List`** to filter and sort those files. The program prompts the user to enter a substring, searches files whose names contain that substring, sorts them alphabetically, and then prints the results.

```haskell
import System.Directory (listDirectory, doesFileExist)
import Data.List (isInfixOf, sort)
import Control.Monad (filterM)

main :: IO ()
main = do
    putStrLn "Enter substring to search for in filenames:"
    substr <- getLine

    -- List all entries in current directory
    entries <- listDirectory "."

    -- Filter only files
    files <- filterM doesFileExist entries

    -- Filter files containing the substring
    let filteredFiles = filter (substr `isInfixOf`) files

    -- Sort the filtered files alphabetically
    let sortedFiles = sort filteredFiles

    putStrLn "\nMatching files (sorted):"
    mapM_ putStrLn sortedFiles
```

---

### Explanation:

* `listDirectory "."` lists all entries (files and directories) in the current directory.
* `filterM doesFileExist entries` filters to keep only files.
* `filter (substr \`isInfixOf\`) files\` keeps files whose names contain the substring entered by the user.
* `sort` from `Data.List` sorts the filtered file list alphabetically.
* Finally, the program prints the sorted filenames.

---


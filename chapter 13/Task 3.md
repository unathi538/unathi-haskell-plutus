
We'll use:

* `Data.List.filter` to filter filenames containing the substring,
* `Data.List.sort` to sort the filtered list,
* and `System.Directory` to list files and check if they exist.

```haskell
import System.Directory (listDirectory, doesFileExist)
import Data.List (filter, sort, isInfixOf)
import Control.Monad (filterM)

-- | Filter files containing the substring and return them sorted alphabetically.
filterAndSortFiles :: String -> IO [FilePath]
filterAndSortFiles substr = do
    entries <- listDirectory "."
    files <- filterM doesFileExist entries
    let filteredFiles = filter (substr `isInfixOf`) files
    return (sort filteredFiles)

main :: IO ()
main = do
    putStrLn "Enter substring to filter files:"
    substr <- getLine
    sortedFiles <- filterAndSortFiles substr
    putStrLn "Filtered and sorted files:"
    mapM_ putStrLn sortedFiles
```

---

### Explanation:

* `listDirectory "."` lists all directory entries.
* `filterM doesFileExist entries` keeps only files.
* `filter (substr \`isInfixOf\`) files\` selects files whose names contain the substring.
* `sort filteredFiles` sorts the filenames alphabetically.
* Finally, the main program prompts for a substring and prints the filtered & sorted filenames.


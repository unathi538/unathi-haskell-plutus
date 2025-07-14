

* Filters file names in the current directory by a substring,
* Converts the filtered list of file names into a `Data.Map` where:

  * The key is the file name,
  * The value is the length of the file name (just as an example of a value),
* Prints the resulting map.

We'll use `Data.Map.Strict` and `System.Directory`.

```haskell
import System.Directory (listDirectory, doesFileExist)
import Data.List (isInfixOf)
import Control.Monad (filterM)
import qualified Data.Map.Strict as Map

-- | Filter files by substring and convert to a Map with filename as key and filename length as value.
filesToMap :: String -> IO (Map.Map FilePath Int)
filesToMap substr = do
    entries <- listDirectory "."
    files <- filterM doesFileExist entries
    let filteredFiles = filter (substr `isInfixOf`) files
        fileMap = Map.fromList [(f, length f) | f <- filteredFiles]
    return fileMap

main :: IO ()
main = do
    putStrLn "Enter substring to filter files:"
    substr <- getLine
    fileMap <- filesToMap substr
    putStrLn "Files mapped to their lengths:"
    mapM_ print (Map.toList fileMap)
```

---

### Explanation:

* `listDirectory "."` gets all entries.
* `filterM doesFileExist` filters to files only.
* `filter (substr \`isInfixOf\`) files\` filters files containing the substring.
* `Map.fromList` creates a map from each filename to its length.
* Finally, the map is printed as a list of key-value pairs.


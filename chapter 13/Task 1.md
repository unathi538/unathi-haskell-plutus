
```haskell
import System.Directory (listDirectory)
import System.FilePath ((</>))
import Control.Monad (filterM)
import System.Directory (doesFileExist)

main :: IO ()
main = do
    -- Get all entries (files and directories) in the current directory
    entries <- listDirectory "."
    
    -- Filter only the files from the entries
    files <- filterM doesFileExist entries
    
    -- Print each file name
    mapM_ putStrLn files
```

### Explanation:

* `listDirectory "."` returns a list of all entries in the current directory (both files and directories).
* `doesFileExist` checks if a given path corresponds to a file.
* `filterM doesFileExist entries` filters the list to include only files.
* `mapM_ putStrLn files` prints each file name on its own line.

This program prints all files (not directories) in the current directory.



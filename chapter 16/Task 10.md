
## Code

```haskell
import qualified Data.Map.Strict as M
import Data.List (foldl', sortOn)
import Data.Ord (Down(..))

-- | Count the frequency of each character in a string.
--   Returns an association list [(char, count)], sorted by descending count.
charFreq :: String -> [(Char, Int)]
charFreq s = sortOn (Down . snd) . M.toList $
             foldl' step M.empty s
  where
    step :: M.Map Char Int -> Char -> M.Map Char Int
    step m ch = M.insertWith (+) ch 1 m
    -- insertWith (+) increments the existing count or inserts 1 if absent

main :: IO ()
main = do
  putStrLn "Enter a string:"
  input <- getLine
  let freqs = charFreq input
  putStrLn "Character frequencies (sorted by frequency desc):"
  mapM_ print freqs
```

---

## Explanation (quick)

* **`charFreq`**:

  * Uses a `Map Char Int` to accumulate counts.
  * `foldl'` (strict left fold) walks through the string once.
  * `M.insertWith (+) ch 1` says: *if `ch` is already in the map, add 1 to its value; otherwise insert it with 1*.
  * Finally, we turn the map into a list with `M.toList` and sort it by **descending counts** using `sortOn (Down . snd)`.

* **`main`**:

  * Reads a line from the user.
  * Calls `charFreq` to compute frequencies.
  * Prints each `(character, count)` pair.


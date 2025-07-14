
### Example: Handling name conflicts between `Data.List` and a custom `MyList` module

Let's assume both modules export a function named `sort`.

---

#### MyList.hs (custom module)

```haskell
module MyList (sort) where

-- A dummy sort function that just returns the list reversed for demonstration
sort :: [Int] -> [Int]
sort = reverse
```

---

#### Main.hs

```haskell
import qualified Data.List as DL    -- qualified import with alias DL
import qualified MyList as ML       -- qualified import with alias ML

main :: IO ()
main = do
    let list = [3, 1, 4, 1, 5, 9]
    
    -- Use Data.List's sort (ascending sort)
    putStrLn "Data.List.sort result:"
    print $ DL.sort list
    
    -- Use MyList's sort (reverse, for demo)
    putStrLn "MyList.sort result:"
    print $ ML.sort list
```

---

### Explanation:

* Both `Data.List` and `MyList` export a function named `sort`.
* We import both **qualified** with aliases: `DL` and `ML`.
* To call each sort, we prefix with the alias: `DL.sort` and `ML.sort`.
* This avoids naming conflicts and makes the code clear.

---



---

### Expected output:

```
Data.List.sort result:
[1,1,3,4,5,9]
MyList.sort result:
[9,5,1,4,1,3]
```

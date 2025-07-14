

### Setup:

* We'll use the standard `Data.List` module (renamed as `ListOps`)
* We'll create a custom module `MyList` with a function that conflicts with `Data.List` (also renamed as `MyOps`)

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
import qualified Data.List as ListOps  -- Renaming Data.List to ListOps
import qualified MyList as MyOps       -- Renaming MyList to MyOps

main :: IO ()
main = do
    let numbers = [10, 5, 7, 3, 8]

    -- Use sort from Data.List (ListOps)
    putStrLn "Sorted with Data.List (ListOps.sort):"
    print $ ListOps.sort numbers

    -- Use sort from MyList (MyOps)
    putStrLn "Sorted with MyList (MyOps.sort):"
    print $ MyOps.sort numbers
```

---

### Explanation:

* We import `Data.List` qualified as `ListOps`.
* We import `MyList` qualified as `MyOps`.
* Both modules export a `sort` function, but since namespaces are renamed, we call them explicitly via `ListOps.sort` and `MyOps.sort`.
* This avoids name conflicts and improves code clarity.

---

### How to run:

1. Save the `MyList.hs` file.
2. Save the `Main.hs` file.
3. Compile with:

   ```bash
   ghc Main.hs MyList.hs
   ```
4. Run the executable.

---

### Expected output:

```
Sorted with Data.List (ListOps.sort):
[3,5,7,8,10]
Sorted with MyList (MyOps.sort):
[8,3,7,5,10]
```

---


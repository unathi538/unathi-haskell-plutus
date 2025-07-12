
* The recursive `Sequence a` data type,
* A function `elemSeq` that checks whether a given element is in the sequence,
* A `main` function that demonstrates how `elemSeq` works.

---

### ✅ **Full Example**

```haskell
-- Define the recursive Sequence data type
data Sequence a = End | Node a (Sequence a) deriving Show

-- Define the elemSeq function
elemSeq :: Eq a => a -> Sequence a -> Bool
elemSeq _ End = False
elemSeq x (Node y ys)
    | x == y    = True
    | otherwise = elemSeq x ys

-- Example usage in main
main :: IO ()
main = do
    -- Create a sequence: 1 -> 2 -> 3 -> End
    let seq1 = Node 1 (Node 2 (Node 3 End))

    -- Check for elements
    putStrLn "Check if 2 is in the sequence:"
    print (elemSeq 2 seq1)  -- True

    putStrLn "Check if 5 is in the sequence:"
    print (elemSeq 5 seq1)  -- False
```

---

### 🔍 Explanation

* `elemSeq :: Eq a => a -> Sequence a -> Bool`:

  * Uses pattern matching and recursion.
  * Returns `True` if the element is found, otherwise keeps checking.
  * `Eq a =>` means the elements must support equality (`==`).

---

### 💡 Output When Run

```
Check if 2 is in the sequence:
True
Check if 5 is in the sequence:
False
```



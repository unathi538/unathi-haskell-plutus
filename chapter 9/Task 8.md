
### ✅ **Full Working Example**

```haskell
-- Define the recursive Sequence data type
data Sequence a = End | Node a (Sequence a) deriving Show

-- Example usage in main
main :: IO ()
main = do
    -- Create a sequence of Ints: 1 -> 2 -> 3 -> End
    let seq1 = Node 1 (Node 2 (Node 3 End))

    -- Create a sequence of Strings: "a" -> "b" -> End
    let seq2 = Node "a" (Node "b" End)

    putStrLn "Sequence of Integers:"
    print seq1

    putStrLn "\nSequence of Strings:"
    print seq2
```

---

### 🔍 Explanation

* `data Sequence a = End | Node a (Sequence a)` defines a recursive data structure:

  * `End` is the end of the sequence (like `null` or `[]`).
  * `Node a next` holds a value and a reference to the next node.
* The structure behaves similarly to a singly linked list.
* `deriving Show` allows printing the sequence to the console.
* `main` constructs and prints two sequences — one of integers, one of strings.

---

### 💡 Output When Run

```
Sequence of Integers:
Node 1 (Node 2 (Node 3 End))

Sequence of Strings:
Node "a" (Node "b" End)
```

---


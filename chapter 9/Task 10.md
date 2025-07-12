
* Constructors for an empty tree and a node,
* A sample tree structure,
* A `main` function that prints the tree.

---

### ✅ **Full Example**

```haskell
-- Define the BST data type
data BST a = Empty
           | Node a (BST a) (BST a)
           deriving Show

-- Example usage in main
main :: IO ()
main = do
    -- Manually construct a BST of integers
    --       5
    --      / \
    --     3   8
    --        / \
    --       6   9
    let tree = Node 5
                  (Node 3 Empty Empty)
                  (Node 8
                      (Node 6 Empty Empty)
                      (Node 9 Empty Empty))

    putStrLn "Binary Search Tree structure:"
    print tree
```

---

### 🔍 Explanation

* `data BST a = Empty | Node a (BST a) (BST a)`:

  * `Empty` represents an empty tree.
  * `Node a left right` holds a value `a`, a left subtree, and a right subtree.
* `deriving Show` allows printing the tree with `print`.

---

### 💡 Sample Output

```
Binary Search Tree structure:
Node 5 (Node 3 Empty Empty) (Node 8 (Node 6 Empty Empty) (Node 9 Empty Empty))
```


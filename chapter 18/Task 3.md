

```haskell
-- Define the binary tree data type
data Tree a = Empty
            | Node a (Tree a) (Tree a)
            deriving (Show)

-- Functor instance for Tree
instance Functor Tree where
  fmap _ Empty = Empty
  fmap f (Node x left right) = Node (f x) (fmap f left) (fmap f right)

-- Function to increment every value in the tree by 1 using fmap
incrementTreeValues :: Num a => Tree a -> Tree a
incrementTreeValues = fmap (+1)

main :: IO ()
main = do
  let tree = Node 10
                (Node 20 Empty Empty)
                (Node 30 (Node 40 Empty Empty) Empty)
  
  putStrLn "Original tree:"
  print tree
  
  let incrementedTree = incrementTreeValues tree
  
  putStrLn "Tree after incrementing each value by 1:"
  print incrementedTree
```

---

### Explanation:

* `incrementTreeValues` uses the `Functor` instance of `Tree` to apply `(+1)` to every element.
* The tree is printed before and after incrementing.
* This cleanly separates the logic for incrementing from the tree structure, reusing the functor implementation.

---


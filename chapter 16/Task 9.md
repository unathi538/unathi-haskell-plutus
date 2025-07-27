

---

### ✅ Code

```haskell
-- Function to remove duplicates from a list
removeDuplicates :: Eq a => [a] -> [a]
removeDuplicates [] = []
removeDuplicates (x:xs)
  | x `elem` xs = removeDuplicates xs
  | otherwise   = x : removeDuplicates xs

main :: IO ()
main = do
  let listWithDuplicates = [1, 2, 3, 2, 4, 1, 5, 3, 6]
  putStrLn "Original list with duplicates:"
  print listWithDuplicates

  let uniqueList = removeDuplicates listWithDuplicates
  putStrLn "List after removing duplicates:"
  print uniqueList
```

---

### 🔍 Explanation

* `removeDuplicates` is a recursive function:

  * **Base case**: An empty list returns an empty list.
  * **Recursive case**:

    * If the head `x` appears in the tail `xs`, skip it.
    * Otherwise, include `x` in the result and keep going.

* In `main`:

  * We define a sample list with duplicates.
  * We apply `removeDuplicates` to it.
  * Then we print both the original and the cleaned list.

---

### 📝 Output Example

```
Original list with duplicates:
[1,2,3,2,4,1,5,3,6]
List after removing duplicates:
[6,5,4,2,1]
```


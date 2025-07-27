
### ✅ Code: Insertion Sort in Haskell

```haskell
-- Insert an element into a sorted list in the correct position
insert :: Int -> [Int] -> [Int]
insert x [] = [x]
insert x (y:ys)
  | x <= y    = x : y : ys
  | otherwise = y : insert x ys

-- Insertion sort: sort a list using the insert function
insertionSort :: [Int] -> [Int]
insertionSort [] = []
insertionSort (x:xs) = insert x (insertionSort xs)

main :: IO ()
main = do
  let unsortedList = [7, 2, 5, 3, 8, 1, 4]
  putStrLn "Original unsorted list:"
  print unsortedList

  let sortedList = insertionSort unsortedList
  putStrLn "Sorted list using insertion sort:"
  print sortedList
```

---

### 🔍 Explanation

#### `insert` function:

* Takes an integer `x` and a sorted list, and inserts `x` into the correct position.
* It recursively walks through the list:

  * If `x <= y`, it places `x` before `y`.
  * Otherwise, continues to insert into the rest of the list.

#### `insertionSort` function:

* Base case: An empty list is already sorted.
* Recursive case: Sort the tail with `insertionSort`, then insert the head using `insert`.

#### `main` function:

* Defines an example unsorted list.
* Applies `insertionSort` to sort it.
* Prints both the original and sorted lists.

---

### 📝 Sample Output

```
Original unsorted list:
[7,2,5,3,8,1,4]
Sorted list using insertion sort:
[1,2,3,4,5,7,8]
```

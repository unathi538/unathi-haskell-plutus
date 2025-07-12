

* Defines a parameterized `Box a` type with `Ord` derived,
* Implements a function `sortContainers` that sorts a list of containers (like `Box a`),
* Demonstrates usage in `main`.

---

### ✅ Full Working Example

```haskell
import Data.List (sort)

-- Define the Box type with deriving Eq and Ord
data Box a = Empty | Has a deriving (Show, Eq, Ord)

-- sortContainers function that sorts a list of containers
sortContainers :: Ord (c a) => [c a] -> [c a]
sortContainers = sort

-- Main function to demonstrate usage
main :: IO ()
main = do
  let boxes = [Has 10, Empty, Has 5, Has 20, Empty]
  putStrLn "Original list:"
  print boxes

  let sortedBoxes = sortContainers boxes
  putStrLn "\nSorted list:"
  print sortedBoxes
```

---

### Explanation

* `Box a` derives `Ord` so we can sort lists of boxes.
* `sortContainers` simply calls `sort` from `Data.List`.
* `Empty` is considered less than any `Has` value, so `Empty` boxes come first.
* `main` shows the original and sorted lists.

---

### Sample Output

```
Original list:
[Has 10,Empty,Has 5,Has 20,Empty]

Sorted list:
[Empty,Empty,Has 5,Has 10,Has 20]
```


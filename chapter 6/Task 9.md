: Implement a function that applies a given function to each element of a list (map implementation).



### ✅ Haskell Code Example

```haskell
-- Custom implementation of map
myMap :: (a -> b) -> [a] -> [b]
myMap _ [] = []
myMap f (x:xs) = f x : myMap f xs

-- Main function to test myMap
main :: IO ()
main = do
    let numbers = [1, 2, 3, 4, 5]
    let doubled = myMap (*2) numbers
    let toString = myMap show numbers

    putStrLn $ "Original list: " ++ show numbers
    putStrLn $ "Doubled: " ++ show doubled
    putStrLn $ "As strings: " ++ show toString
```

---

### 🧠 Explanation:

* `myMap` takes:

  * A function `f` (e.g., `(*2)`)
  * A list `[a]`
* It applies `f` to the head of the list and recurses over the tail.
* The result is a new list with the function applied to every element.

---

### 💡 Sample Output:

```
Original list: [1,2,3,4,5]
Doubled: [2,4,6,8,10]
As strings: ["1","2","3","4","5"]
```



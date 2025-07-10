-- HC6T6: Implement a function that determines whether a given element exists in a list.



### ✅ Haskell Code Example

```haskell
-- Function to check if an element exists in a list
elementExists :: Eq a => a -> [a] -> Bool
elementExists _ [] = False
elementExists x (y:ys)
    | x == y    = True
    | otherwise = elementExists x ys

-- Main function to test the above function
main :: IO ()
main = do
    let list = [1, 2, 3, 4, 5]
    let item1 = 3
    let item2 = 7

    putStrLn $ "Does " ++ show item1 ++ " exist in the list? " ++ show (elementExists item1 list)
    putStrLn $ "Does " ++ show item2 ++ " exist in the list? " ++ show (elementExists item2 list)
```

---

### 🧠 Explanation:

* `elementExists` takes two arguments:

  * The element you're looking for (`x`)
  * The list to search in (`[a]`)
* It uses **pattern matching** and **recursion**:

  * If the list is empty, return `False`.
  * If the head of the list (`y`) equals `x`, return `True`.
  * Otherwise, check the rest of the list (`ys`).

---

### 💡 Example Output when you run it:

```
Does 3 exist in the list? True
Does 7 exist in the list? False
```




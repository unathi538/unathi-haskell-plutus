 HC6T7: Implement a function that takes a list and returns the length of the list.


### ✅ Haskell Code Example

```haskell
-- Function to compute the length of a list
myLength :: [a] -> Int
myLength [] = 0
myLength (_:xs) = 1 + myLength xs

-- Main function to test myLength
main :: IO ()
main = do
    let list1 = [10, 20, 30, 40]
    let list2 = "hello"

    putStrLn $ "Length of list1: " ++ show (myLength list1)
    putStrLn $ "Length of list2: " ++ show (myLength list2)
```

---

### 🧠 Explanation:

* `myLength` uses **pattern matching**:

  * If the list is empty `[]`, its length is `0`.
  * If the list has a head and tail (`_:xs`), add 1 and recurse on the tail `xs`.
* This mimics how the built-in `length` function works internally.

---

### 💡 Sample Output:

```
Length of list1: 4
Length of list2: 5
```



-- HC6T8: Implement a function that filters all even numbers from a list.




### ✅ Haskell Code Example

```haskell
-- Function to filter even numbers from a list
filterEvens :: [Int] -> [Int]
filterEvens [] = []
filterEvens (x:xs)
    | even x    = x : filterEvens xs
    | otherwise = filterEvens xs

-- Main function to test filterEvens
main :: IO ()
main = do
    let numbers = [1..10]
    putStrLn $ "Original list: " ++ show numbers
    putStrLn $ "Even numbers: " ++ show (filterEvens numbers)
```

---

### 🧠 Explanation:

* `filterEvens` checks each number in the list:

  * If the number is even (`even x`), it's added to the result.
  * If it's odd, it is skipped.
* Recursively processes the rest of the list (`xs`).

---

### 💡 Sample Output:

```
Original list: [1,2,3,4,5,6,7,8,9,10]
Even numbers: [2,4,6,8,10]
```

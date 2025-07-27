

### Code

```haskell
-- Function to filter even numbers from a list
filterEven :: [Int] -> [Int]
filterEven xs = filter even xs

main :: IO ()
main = do
  let numbers = [1..20]  -- Sample list from 1 to 20
  putStrLn "Original list:"
  print numbers
  
  let evens = filterEven numbers
  putStrLn "Filtered even numbers:"
  print evens
```

---

### Explanation:

* `filterEven` uses the built-in `filter` function with the predicate `even` to select only even numbers.
* In `main`, we define a sample list `[1..20]`.
* We print the original list.
* We apply `filterEven` to get only even numbers.
* We print the filtered list.

---



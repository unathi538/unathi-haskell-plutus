HC5T10: Combining Higher-Order Functions


```haskell
-- Function to check if any squared value is greater than 50
anySquareGreaterThan50 :: [Int] -> Bool
anySquareGreaterThan50 xs = any (>50) (map (^2) (filter (>0) xs))

-- Main function to test it
main :: IO ()
main = do
    let list1 = [1, 2, 3, 4, 5]
    let list2 = [8, 1, 2]
    putStrLn $ "Any square > 50 in list1? " ++ show (anySquareGreaterThan50 list1)
    putStrLn $ "Any square > 50 in list2? " ++ show (anySquareGreaterThan50 list2)
```

### Explanation:

* `filter (>0) xs` filters the list to keep only positive numbers (optional, but included to show `filter` usage).
* `map (^2)` squares each remaining number.
* `any (>50)` checks if any squared value is greater than 50.

### Expected output:

```
Any square > 50 in list1? False
Any square > 50 in list2? True
```


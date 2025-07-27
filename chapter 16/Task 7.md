

### Code

```haskell
-- Function to check if an element exists in a list
elementExists :: Eq a => a -> [a] -> Bool
elementExists = elem

main :: IO ()
main = do
  let sampleList = [1, 3, 5, 7, 9]
  putStrLn "Sample list: [1, 3, 5, 7, 9]"
  
  putStrLn "Enter a number to check if it exists in the list:"
  input <- getLine
  let maybeNum = reads input :: [(Int, String)]
  case maybeNum of
    [(num, "")] -> 
      if elementExists num sampleList
      then putStrLn $ show num ++ " exists in the list."
      else putStrLn $ show num ++ " does not exist in the list."
    _ -> putStrLn "Invalid input. Please enter a valid integer."
```

---

### Explanation:

* `elementExists` is a simple wrapper around the built-in `elem` function, which checks if an element is in a list. The type `Eq a => a -> [a] -> Bool` means it works for any type `a` that supports equality.
* In `main`:

  * We define a sample list `[1,3,5,7,9]`.
  * We prompt the user to enter a number.
  * We safely parse the input with `reads`.
  * If parsing succeeds, we check if the number exists in the list and print the result.
  * Otherwise, we print an error message.

---


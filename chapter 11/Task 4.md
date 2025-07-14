

```haskell
-- ConcatenateLines.hs

main :: IO ()
main = do
    putStrLn "Enter the first line:"
    line1 <- getLine
    putStrLn "Enter the second line:"
    line2 <- getLine
    let result = line1 ++ line2
    putStrLn ("Concatenated result: " ++ result)
```

### Explanation:

* `getLine` reads each line as a string.
* `++` is used to concatenate the two strings.
* `putStrLn` prints the final result.

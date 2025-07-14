
```haskell
-- ReverseString.hs

main :: IO ()
main = do
    putStrLn "Enter a string to reverse:"
    input <- getLine
    let reversed = reverse input
    putStrLn ("Reversed string: " ++ reversed)
```

### Explanation:

* `getLine` reads the user's input as a string.
* `reverse` is a built-in Haskell function that reverses a list — and since a string is just a list of characters, it works perfectly.
* The result is printed using `putStrLn`.


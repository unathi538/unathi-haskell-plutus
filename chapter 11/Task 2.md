
```haskell
-- CountCharacters.hs

main :: IO ()
main = do
    putStrLn "Enter a line of text:"
    line <- getLine
    let count = length line
    putStrLn ("The number of characters in that line is: " ++ show count)
```

### Explanation:

* `getLine` reads the full line of text entered by the user.
* `length line` calculates the number of characters.
* `show count` converts the integer to a string so it can be printed.

### How to Run:

Save this code in a file named `CountCharacters.hs`, then run it with:

```bash
runhaskell CountCharacters.hs
```


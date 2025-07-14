
```haskell
-- Greeting.hs

main :: IO ()
main = do
    putStrLn "What is your name?"
    name <- getLine
    putStrLn ("Hello, " ++ name ++ "! Nice to meet you.")
```

### How It Works:

* `putStrLn` prints a message to the console.
* `getLine` waits for the user to type something and presses Enter, then stores the input in the `name` variable.
* We then greet the user using string concatenation (`++`).

### To Run:

Save it to a file called `Greeting.hs`, then run it using:

```bash
runhaskell Greeting.hs
```


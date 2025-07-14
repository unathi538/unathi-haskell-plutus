

1. Displays a list of options to the user.
2. Waits for their choice.
3. Executes different code based on what they select.

```haskell
-- MenuOptions.hs

main :: IO ()
main = do
    putStrLn "Please choose an option:"
    putStrLn "1. Say Hello"
    putStrLn "2. Show a fun fact"
    putStrLn "3. Exit"
    putStrLn "Enter the number of your choice:"
    choice <- getLine
    handleChoice choice

handleChoice :: String -> IO ()
handleChoice choice = case choice of
    "1" -> putStrLn "Hello there! 👋"
    "2" -> putStrLn "Did you know? Haskell is named after Haskell Curry, a logician."
    "3" -> putStrLn "Goodbye!"
    _   -> do
        putStrLn "Invalid choice. Please enter 1, 2, or 3."
        main  -- restart the menu
```

### How It Works:

* Displays a simple menu.
* Reads user input via `getLine`.
* Uses a `case` expression in `handleChoice` to run different code depending on the input.
* If the input is invalid, it shows an error and restarts.


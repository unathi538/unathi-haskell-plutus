
```haskell
-- RepeatUntilQuit.hs

main :: IO ()
main = do
    putStrLn "Enter something (type 'quit' to exit):"
    loop

loop :: IO ()
loop = do
    input <- getLine
    if input == "quit"
        then putStrLn "Goodbye!"
        else do
            putStrLn ("You entered: " ++ input)
            loop
```

### Explanation:

* The `main` function starts the program and calls `loop`.
* `loop` reads input and checks if it equals `"quit"`.
* If it doesn't, it prints what the user entered and calls itself again.
* If it does, it exits with a goodbye message.



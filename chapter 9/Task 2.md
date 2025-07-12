
```haskell
-- Define the Box data type
data Box a = Empty | Has a deriving Show

-- Example usage in main
main :: IO ()
main = do
    -- Create an empty box
    let emptyBox = (Empty :: Box Int)
    putStrLn "Empty box:"
    print emptyBox

    -- Create a box with a value
    let fullBox = Has 42
    putStrLn "Box with a value:"
    print fullBox

    -- Box of a different type
    let stringBox = Has "Hello, world!"
    putStrLn "Box with a string:"
    print stringBox
```

### Explanation:

* `data Box a = Empty | Has a` defines a polymorphic type `Box a`, which can either be `Empty` or contain a value of type `a`.
* `deriving Show` allows the box to be printed with `print`.
* `main` demonstrates:

  * Creating an `Empty` box explicitly typed as `Box Int`.
  * Creating a `Box Int` with the value `42`.
  * Creating a `Box String` with `"Hello, world!"`.

### Output when run:

```
Empty box:
Empty
Box with a value:
Has 42
Box with a string:
Has "Hello, world!"
```


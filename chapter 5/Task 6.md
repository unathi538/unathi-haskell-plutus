HC5T6: Function Composition

Here's a working Haskell example that uses **function composition (`.`)** to define a function that:

1. Squares each number in a list,
2. Then filters the list to keep only even numbers.

```haskell
-- Function composition to square numbers and filter even ones
squareEvens :: [Int] -> [Int]
squareEvens = filter even . map (^2)

-- Main function to test it
main :: IO ()
main = do
    let numbers = [1..10]
    putStrLn "Even squares from 1 to 10:"
    print (squareEvens numbers)
```

### Explanation:

* `map (^2)` squares each element in the list.
* `filter even` keeps only the even numbers.
* `filter even . map (^2)` composes these two functions.
* `squareEvens [1..10]` returns `[4,16,36,64,100]`.

**Expected Output:**

```
Even squares from 1 to 10:
[4,16,36,64,100]
```

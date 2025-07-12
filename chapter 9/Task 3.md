
* The `Box a` data type,
* A function `addN` that adds a number to a value inside a `Box`,
* And a `main` function that demonstrates it in action.

---

### ✅ **Full Example**

```haskell
-- Define the Box data type
data Box a = Empty | Has a deriving Show

-- Define the addN function
addN :: Num a => a -> Box a -> Box a
addN n Empty     = Empty
addN n (Has x)   = Has (n + x)

-- Example usage in main
main :: IO ()
main = do
    let box1 = Has 10
    let box2 = Empty :: Box Int

    -- Apply addN
    let result1 = addN 5 box1
    let result2 = addN 5 box2

    putStrLn "Original box1:"
    print box1

    putStrLn "After adding 5 to box1:"
    print result1

    putStrLn "Original box2 (empty):"
    print box2

    putStrLn "After adding 5 to box2 (should still be empty):"
    print result2
```

---

### 🔍 Explanation

* `addN :: Num a => a -> Box a -> Box a`:

  * If the box is `Empty`, it stays `Empty`.
  * If it has a number `x`, the result is `Has (n + x)`.

---

### 💡 Sample Output

```
Original box1:
Has 10
After adding 5 to box1:
Has 15
Original box2 (empty):
Empty
After adding 5 to box2 (should still be empty):
Empty
```


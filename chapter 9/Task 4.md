

* The `Box a` data type,
* A function `extract` that returns the value from a `Box`, or a default if it's `Empty`,
* And a `main` function that demonstrates how it works.

---

### ✅ **Full Example**

```haskell
-- Define the Box data type
data Box a = Empty | Has a deriving Show

-- Define the extract function
extract :: a -> Box a -> a
extract defaultValue Empty    = defaultValue
extract _           (Has x)   = x

-- Example usage in main
main :: IO ()
main = do
    let box1 = Has 42
    let box2 = Empty :: Box Int

    let val1 = extract 0 box1
    let val2 = extract 0 box2

    putStrLn "Box with a value:"
    print box1
    putStrLn $ "Extracted value (default 0): " ++ show val1

    putStrLn "\nEmpty box:"
    print box2
    putStrLn $ "Extracted value (default 0): " ++ show val2
```

---

### 🔍 Explanation

* `extract :: a -> Box a -> a`:

  * If the `Box` is `Empty`, return the given default value.
  * If the `Box` has a value, return that value.

---

### 💡 Output When Run

```
Box with a value:
Has 42
Extracted value (default 0): 42

Empty box:
Empty
Extracted value (default 0): 0
```

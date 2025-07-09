HC4T6 - Task 6: Identify List Contents Using Pattern Matching


### ✅ Haskell Code with Explanation

```haskell
-- Function to return the first and third elements of a list
firstAndThird :: [a] -> Maybe (a, a)
firstAndThird (x:_:z:_) = Just (x, z)   -- Pattern matches at least 3 elements
firstAndThird _         = Nothing       -- Not enough elements, return Nothing

-- Main function to test firstAndThird
main :: IO ()
main = do
    print (firstAndThird [1, 2, 3, 4])      -- Just (1, 3)
    print (firstAndThird ["a", "b", "c"])   -- Just ("a", "c")
    print (firstAndThird [42])             -- Nothing
    print (firstAndThird [])               -- Nothing
```

---

### 🧠 Explanation

* **Function signature**:

  ```haskell
  firstAndThird :: [a] -> Maybe (a, a)
  ```

  * Takes a list of any type `[a]`.
  * Returns `Just (first, third)` if at least 3 elements exist.
  * Returns `Nothing` otherwise.

* **Pattern matching**:

  * `(x:_:z:_)` matches the first (`x`), skips the second (`_`), grabs the third (`z`), ignores the rest (`_`).
  * `_` is the fallback for shorter lists.

* **`Maybe` type**:

  * Used to safely handle cases where the list doesn't have enough elements.

---

### 🧪 How to Run

1. Save the code as `FirstAndThird.hs`
2. Compile and run:

```bash
ghc FirstAndThird.hs -o firstthird
./firstthird
```

---

### 🖨️ Sample Output

```
Just (1,3)
Just ("a","c")
Nothing
Nothing
```


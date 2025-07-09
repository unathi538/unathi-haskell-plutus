HC4T8 - Task 8: Extract Values from Tuples


### ✅ Haskell Code with Explanation

```haskell
-- Function that extracts and describes values from a tuple
describeTuple :: (String, Int) -> String
describeTuple (name, age) = name ++ " is " ++ show age ++ " years old."

-- Main function to test describeTuple
main :: IO ()
main = do
    putStrLn (describeTuple ("Alice", 30))
    putStrLn (describeTuple ("Bob", 25))
    putStrLn (describeTuple ("Charlie", 40))
```

---

### 🧠 Explanation

* **Function signature**:

  ```haskell
  describeTuple :: (String, Int) -> String
  ```

  It takes a tuple with a `String` (e.g., a name) and an `Int` (e.g., an age) and returns a `String`.

* **Pattern Matching**:

  * `(name, age)` extracts the values from the tuple.
  * `++` is used to concatenate strings.
  * `show` converts the `Int` value (`age`) to a `String`.

---



### 🖨️ Sample Output

```
Alice is 30 years old.
Bob is 25 years old.
Charlie is 40 years old.
```


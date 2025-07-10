
* A `Describable` type class with a `describe` method.
* A function `describeAndCompare` that:

  * Takes **two values** of a type that is both `Describable` and `Ord`.
  * **Returns the description** of the larger value using `describe`.

---

### ✅ Haskell Code Example

```haskell
-- Define the Describable type class
class Describable a where
    describe :: a -> String

-- Implement Describable for Bool
instance Describable Bool where
    describe True  = "This is true."
    describe False = "This is false."

-- Implement Describable for Int
instance Describable Int where
    describe n = "The number is " ++ show n

-- Function to describe and compare two values
describeAndCompare :: (Describable a, Ord a) => a -> a -> String
describeAndCompare x y
    | x >= y    = describe x
    | otherwise = describe y

-- Main function to test describeAndCompare
main :: IO ()
main = do
    putStrLn $ "Compare Ints 10 and 20: " ++ describeAndCompare (10 :: Int) (20 :: Int)
    putStrLn $ "Compare Bools True and False: " ++ describeAndCompare True False
```

---

### 🧠 Explanation:

* `describeAndCompare` requires that the type is both:

  * `Describable` — so it can describe values
  * `Ord` — so it can compare values using `>=`
* The `Int` and `Bool` types both have `Ord` instances by default.
* We provide custom `Describable` implementations for both.

---

### 💡 Sample Output:

```
Compare Ints 10 and 20: The number is 20
Compare Bools True and False: This is true.
```



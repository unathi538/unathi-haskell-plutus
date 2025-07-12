
* Defines a **subclass `AdvancedEq` of `Eq`**,
* Adds a new method `compareEquality :: a -> a -> Bool`,
* Implements it for a custom `User` type,
* Includes a `main` function to demonstrate how it works.

---

### ✅ Full Working Example

```haskell
-- Define a User data type
data User = User
  { userId :: Int
  , userName :: String
  } deriving (Show, Eq)

-- Define AdvancedEq as a subclass of Eq
class Eq a => AdvancedEq a where
  compareEquality :: a -> a -> Bool

-- Implement AdvancedEq for User
instance AdvancedEq User where
  compareEquality x y = x == y  -- delegates to standard (==)

-- Main function to demonstrate usage
main :: IO ()
main = do
  let user1 = User 1 "Alice"
  let user2 = User 1 "Alice"
  let user3 = User 2 "Bob"

  putStrLn "Compare user1 and user2:"
  print (compareEquality user1 user2)  -- True

  putStrLn "Compare user1 and user3:"
  print (compareEquality user1 user3)  -- False
```

---

### 🔍 Explanation

* `AdvancedEq` is a **subclass** of `Eq`, meaning any type that is `AdvancedEq` must also be an instance of `Eq`.
* `compareEquality` is a custom method added on top of standard equality.
* In the `User` instance, we just delegate to `(==)`, but this method could include custom logic (e.g., ignore case, only compare `userId`, etc.).

---

### 💡 Sample Output

```
Compare user1 and user2:
True
Compare user1 and user3:
False
```


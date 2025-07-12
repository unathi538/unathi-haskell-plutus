Define a type class ShowDetailed with a function showDetailed :: a -> String and implement it for a type User.



* Defines a type class `ShowDetailed` with a function `showDetailed :: a -> String`,
* Defines a `User` type with some fields,
* Implements the `ShowDetailed` instance for `User`,
* Includes a `main` function that demonstrates its usage.

---

### ✅ Full Working Example

```haskell
-- Define the ShowDetailed type class
class ShowDetailed a where
  showDetailed :: a -> String

-- Define a User data type
data User = User
  { name  :: String
  , age   :: Int
  , email :: String
  } deriving Show

-- Implement ShowDetailed for User
instance ShowDetailed User where
  showDetailed (User n a e) =
    "User Details:\n" ++
    "Name: " ++ n ++ "\n" ++
    "Age: " ++ show a ++ "\n" ++
    "Email: " ++ e

-- Main function to demonstrate usage
main :: IO ()
main = do
  let user1 = User "Alice" 30 "alice@example.com"
  putStrLn $ showDetailed user1
```

---

### 🔍 Explanation

* `ShowDetailed` is a custom type class like `Show`, but more flexible for detailed formatting.
* `User` is a record type with `name`, `age`, and `email` fields.
* `showDetailed` returns a nicely formatted string with multiple lines.
* `main` creates a sample user and prints the detailed info using `showDetailed`.

---

### 💡 Sample Output

```
User Details:
Name: Alice
Age: 30
Email: alice@example.com
```


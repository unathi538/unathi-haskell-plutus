

* Defines a type class `Concatenatable` with a method `concatWith :: a -> a -> a`,
* Provides an instance for `[Char]` (i.e. `String`),
* Includes a `main` function to demonstrate its usage.

---

### ✅ Full Working Example

```haskell
-- Define the Concatenatable type class
class Concatenatable a where
  concatWith :: a -> a -> a

-- Implement Concatenatable for String ([Char])
instance Concatenatable [Char] where
  concatWith = (++)

-- Main function to demonstrate usage
main :: IO ()
main = do
  let str1 = "Hello, "
  let str2 = "world!"
  let result = concatWith str1 str2

  putStrLn "Concatenated result:"
  putStrLn result
```

---

### 🔍 Explanation

* `Concatenatable` is a custom type class that defines `concatWith` for types that can be joined.
* For `[Char]`, which is the type alias for `String`, we use the standard `(++)` operator.
* `main` combines two strings and prints the result.

---

### 💡 Sample Output

```
Concatenated result:
Hello, world!
```


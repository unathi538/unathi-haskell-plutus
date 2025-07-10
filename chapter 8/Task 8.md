

* Defines two **type synonyms**:

  * `Name` for `String`
  * `Age` for `Int`
* Implements the function `greet :: Name -> Age -> String`
* Includes a `main` function to demonstrate how it works

---

### ✅ Haskell Code Example

```haskell
-- Type synonyms
type Name = String
type Age  = Int

-- Function to generate a greeting
greet :: Name -> Age -> String
greet name age = "Hello, " ++ name ++ "! You are " ++ show age ++ " years old."

-- Main function to test greet
main :: IO ()
main = do
    let personName = "Alice"
    let personAge  = 28
    putStrLn (greet personName personAge)
```

---

### 💡 Sample Output

```
Hello, Alice! You are 28 years old.
```

---



* Defines a `Person` type using **record syntax** with fields:

  * `name :: String`
  * `age :: Int`
  * `isEmployed :: Bool`
* Creates two sample persons:

  * `person1` who **is employed**
  * `person2` who **is unemployed**
* Prints their details in the `main` function.

---

### ✅ Haskell Code Example

```haskell
-- Define the Person data type using record syntax
data Person = Person
  { name :: String
  , age :: Int
  , isEmployed :: Bool
  } deriving (Show)

-- Create an employed person
person1 :: Person
person1 = Person
  { name = "Alice"
  , age = 30
  , isEmployed = True
  }

-- Create an unemployed person
person2 :: Person
person2 = Person
  { name = "Bob"
  , age = 25
  , isEmployed = False
  }

-- Main function to display person info
main :: IO ()
main = do
  putStrLn "Person 1:"
  putStrLn $ "Name: " ++ name person1
  putStrLn $ "Age: " ++ show (age person1)
  putStrLn $ "Employed: " ++ show (isEmployed person1)

  putStrLn "\nPerson 2:"
  putStrLn $ "Name: " ++ name person2
  putStrLn $ "Age: " ++ show (age person2)
  putStrLn $ "Employed: " ++ show (isEmployed person2)
```

---

### 💡 Sample Output:

```
Person 1:
Name: Alice
Age: 30
Employed: True

Person 2:
Name: Bob
Age: 25
Employed: False
```


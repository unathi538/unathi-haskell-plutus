

* Defines a new type `Employee` using **record syntax** with fields:

  * `name :: String`
  * `experienceInYears :: Float`
* Creates an `Employee` named **richard** with **7.5 years** of experience.
* Includes a `main` function to display the data.

---

### ✅ Haskell Code Example

```haskell
-- Define the Employee data type using record syntax
data Employee = Employee
  { name :: String
  , experienceInYears :: Float
  } deriving (Show)

-- Create an employee named Richard with 7.5 years of experience
richard :: Employee
richard = Employee
  { name = "Richard"
  , experienceInYears = 7.5
  }

-- Main function to display Richard's information
main :: IO ()
main = do
  putStrLn $ "Employee Name: " ++ name richard
  putStrLn $ "Experience: " ++ show (experienceInYears richard) ++ " years"
```

---

### 💡 Sample Output:

```
Employee Name: Richard
Experience: 7.5 years
```

---



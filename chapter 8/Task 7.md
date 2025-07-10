
* Defines a new `Animal` type using `data` with constructors `Dog String` and `Cat String`
* Implements the function `describeAnimal :: Animal -> String` to describe the animal
* Creates instances of a dog and a cat
* Includes a `main` function to run and print the output

---

### ✅ Haskell Code Example

```haskell
-- Define the Animal data type
data Animal = Dog String | Cat String deriving (Show)

-- Function to describe an animal
describeAnimal :: Animal -> String
describeAnimal (Dog name) = "This is a dog named " ++ name ++ "."
describeAnimal (Cat name) = "This is a cat named " ++ name ++ "."

-- Create instances of animals
myDog :: Animal
myDog = Dog "Max"

myCat :: Animal
myCat = Cat "Luna"

-- Main function to run and show descriptions
main :: IO ()
main = do
    putStrLn $ describeAnimal myDog
    putStrLn $ describeAnimal myCat
```

---

### 💡 Sample Output

```
This is a dog named Max.
This is a cat named Luna.
```

---


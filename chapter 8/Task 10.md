
* Defines a `Book` type using **record syntax** with fields:

  * `title :: String`
  * `author :: String`
  * `year :: Int`
* Uses `deriving Show` to automatically allow the book to be printed.
* Creates an instance of `Book` and prints it in `main`.

---

### ✅ Haskell Code Example

```haskell
-- Define the Book type with Show deriving
data Book = Book
  { title  :: String
  , author :: String
  , year   :: Int
  } deriving (Show)

-- Create a sample book instance
myBook :: Book
myBook = Book
  { title = "The Haskell Way"
  , author = "Jane Functional"
  , year = 2025
  }

-- Main function to print the book using Show
main :: IO ()
main = do
  putStrLn "Book Info:"
  print myBook
```

---

### 💡 Sample Output:

```
Book Info:
Book {title = "The Haskell Way", author = "Jane Functional", year = 2025}
```


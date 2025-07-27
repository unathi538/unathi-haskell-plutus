

## ✅ Full Working Code

```haskell
-- Function that combines two lists using Semigroup instance
combineLists :: [Int] -> [Int] -> [Int]
combineLists = (<>)

main :: IO ()
main = do
  let list1 = [1, 2, 3]
      list2 = [4, 5, 6]

  putStrLn "List 1:"
  print list1

  putStrLn "List 2:"
  print list2

  let combined = combineLists list1 list2

  putStrLn "Combined list using Semigroup (<>) operator:"
  print combined
```

---

## 🔍 Explanation

### 🔹 Semigroup for Lists

Haskell defines:

```haskell
instance Semigroup [a] where
  (<>) = (++)
```

This means `(<>)` acts like the standard list append operator `(++)`.

### 🔹 `combineLists` function

```haskell
combineLists :: [Int] -> [Int] -> [Int]
combineLists = (<>)
```

Takes two lists of `Int` and returns their concatenation using the Semigroup operator.

### 🔹 `main`

* Creates two lists of integers.
* Uses `combineLists` to concatenate them.
* Prints the result.

---


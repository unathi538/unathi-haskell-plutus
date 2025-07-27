

```haskell
-- Function to convert Bool to '1' or '0'
boolToBit :: Bool -> Char
boolToBit True  = '1'
boolToBit False = '0'

-- Use fmap to apply boolToBit to every element in the list
mapToBits :: [Bool] -> [Char]
mapToBits = fmap boolToBit

main :: IO ()
main = do
  let boolList = [True, False, True, True, False]
  putStrLn "Original Bool list:"
  print boolList

  let bitString = mapToBits boolList
  putStrLn "Converted to bits (as characters):"
  print bitString
```

---

### Explanation:

* `boolToBit` converts a single `Bool` to `'1'` or `'0'`.
* `mapToBits` uses `fmap` (which for lists is the same as `map`) to apply `boolToBit` to each element.
* The `main` function demonstrates this by printing the original list and the resulting character list.

---


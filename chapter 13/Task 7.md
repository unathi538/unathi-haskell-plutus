Sure! Here’s a simple example where you import the `sumNonEmpty` function from your custom `SumNonEmpty` module and use it in `main` to calculate the sum of a list.

---

### SumNonEmpty.hs (your custom module)

```haskell
module SumNonEmpty (sumNonEmpty) where

sumNonEmpty :: Num a => [a] -> a
sumNonEmpty [] = error "sumNonEmpty: empty list"
sumNonEmpty xs = sum xs
```

---

### Main.hs (the program using SumNonEmpty)

```haskell
import SumNonEmpty (sumNonEmpty)

main :: IO ()
main = do
    let numbers = [10, 20, 30, 40]
    putStrLn $ "The sum of " ++ show numbers ++ " is:"
    print $ sumNonEmpty numbers
```

---

### Explanation:

* `SumNonEmpty` module exports `sumNonEmpty`.
* `main` imports `sumNonEmpty` and uses it to sum a predefined list `[10,20,30,40]`.
* The program prints the list and its sum.

---



You should see:

```
The sum of [10,20,30,40] is:
100
```

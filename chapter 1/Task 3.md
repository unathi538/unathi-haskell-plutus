HC1T3 - Task 3: Checking if a Number is Greater than 18



```haskell
-- Define the function
greaterThan18 :: Int -> Bool
greaterThan18 x = x > 18

-- Main function to test greaterThan18
main :: IO ()
main = do
    let number = 20
    putStrLn ("Number: " ++ show number)
    putStrLn ("Is greater than 18? " ++ show (greaterThan18 number))
```

### Explanation:

* `greaterThan18` takes an integer and returns `True` if it's greater than 18, otherwise `False`.
* The `main` function tests it with the number `20`.

### Sample Output:

```
Number: 20
Is greater than 18? True
```



HC6T10: Implement a recursive function that takes a number and returns a list of its digits.



### ✅ Haskell Code Example

```haskell
-- Function to get the list of digits of a number
digits :: Int -> [Int]
digits n
    | n < 10    = [n]
    | otherwise = digits (n `div` 10) ++ [n `mod` 10]

-- Main function to test digits
main :: IO ()
main = do
    let number1 = 12345
    let number2 = 908

    putStrLn $ "Digits of " ++ show number1 ++ ": " ++ show (digits number1)
    putStrLn $ "Digits of " ++ show number2 ++ ": " ++ show (digits number2)
```

---

### 🧠 Explanation:

* The function `digits` works recursively:

  * Base case: if `n` is less than 10, it’s a single digit, so return `[n]`.
  * Recursive case: divide the number by 10 (`n `div` 10`) and append the last digit (`n `mod` 10`) to the result.
* `++` is used to concatenate the recursive result with the last digit.

---

### 💡 Sample Output:

```
Digits of 12345: [1,2,3,4,5]
Digits of 908: [9,0,8]
```



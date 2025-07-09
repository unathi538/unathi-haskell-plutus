HC3T1 - Task 1: Check if a number is positive, negative, or zero


---

### ✅ **Haskell Code Example**

```haskell
-- Define the function with its type signature
checkNumber :: Int -> String
checkNumber n = 
    if n > 0 then "Positive"
    else if n < 0 then "Negative"
    else "Zero"

-- Main function to test the checkNumber function
main :: IO ()
main = do
    putStrLn ("checkNumber 5 = " ++ checkNumber 5)
    putStrLn ("checkNumber (-3) = " ++ checkNumber (-3))
    putStrLn ("checkNumber 0 = " ++ checkNumber 0)
```

---



---

### 🖨️ Sample Output

```
checkNumber 5 = Positive
checkNumber (-3) = Negative
checkNumber 0 = Zero
```



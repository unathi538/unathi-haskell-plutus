HC3T6 - Advanced Task 6: Check leap year using if-then-else

Here's a complete and working Haskell program that defines the function `isLeapYear :: Int -> Bool` using **`if-then-else`** logic to check for leap years based on the Gregorian calendar rules.

---

### ✅ **Haskell Code with Explanation**

```haskell
-- Function to determine whether a year is a leap year
isLeapYear :: Int -> Bool
isLeapYear year =
    if year `mod` 400 == 0 then True
    else if year `mod` 100 == 0 then False
    else if year `mod` 4 == 0 then True
    else False

-- Main function to test isLeapYear
main :: IO ()
main = do
    let y1 = isLeapYear 2000    -- Divisible by 400 → True
    let y2 = isLeapYear 1900    -- Divisible by 100 but not 400 → False
    let y3 = isLeapYear 2024    -- Divisible by 4 → True
    putStrLn ("isLeapYear 2000 = " ++ show y1)
    putStrLn ("isLeapYear 1900 = " ++ show y2)
    putStrLn ("isLeapYear 2024 = " ++ show y3)
```

---

### 🧠 **Explanation**

The leap year rules:

1. A year is a **leap year** if it is divisible by **400**.
2. If it is divisible by **100 but not 400**, it is **not** a leap year.
3. If it is divisible by **4**, it **is** a leap year.
4. Otherwise, it is **not** a leap year.

The `if-then-else` structure checks these conditions **in order**, using the `%` operator (`mod`) to check divisibility.

---



### 🖨️ Sample Output

```
isLeapYear 2000 = True
isLeapYear 1900 = False
isLeapYear 2024 = True
```


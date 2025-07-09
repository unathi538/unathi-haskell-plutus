 HC4T5 - Task 5: Add a Catch-All Pattern with a Custom Message

 Certainly! Below is a **working Haskell code example** of a function `specialBirthday :: Int -> String`. It checks for **predefined special ages** and, for all other ages, returns a **custom message including the age**.

---

### ✅ Haskell Code with Explanation

```haskell
-- Function that returns a special message based on age
specialBirthday :: Int -> String
specialBirthday age
    | age == 1  = "Happy 1st Birthday!"
    | age == 18 = "Congratulations on becoming an adult!"
    | age == 21 = "Cheers to 21! Enjoy responsibly!"
    | age == 50 = "Half a century! Amazing!"
    | otherwise = "Happy " ++ show age ++ "th Birthday!"  -- Include age in the message

-- Main function to test specialBirthday
main :: IO ()
main = do
    putStrLn (specialBirthday 1)
    putStrLn (specialBirthday 18)
    putStrLn (specialBirthday 21)
    putStrLn (specialBirthday 50)
    putStrLn (specialBirthday 7)     -- Not predefined
    putStrLn (specialBirthday 30)    -- Not predefined
```

---

### 🧠 Explanation

* The function uses **guards** to check specific ages (1, 18, 21, 50).
* For all other ages, the `otherwise` clause is used.

  * It includes the age dynamically using `show age` to convert the number to a string.
  * Example: if `age = 7`, the result will be `"Happy 7th Birthday!"`.

---



### 🖨️ Sample Output

```
Happy 1st Birthday!
Congratulations on becoming an adult!
Cheers to 21! Enjoy responsibly!
Half a century! Amazing!
Happy 7th Birthday!
Happy 30th Birthday!
```


HC5T9: Higher-Order Function to Transform a List


### ✅ Haskell Code:

```haskell
-- Define transformList to apply a function twice to each element
transformList :: (a -> a) -> [a] -> [a]
transformList f = map (f . f)

-- Example function: double a number
double :: Int -> Int
double x = x * 2

-- Main function to test transformList
main :: IO ()
main = do
    let numbers = [1, 2, 3, 4, 5]
    putStrLn "Applying (double . double) to each element:"
    print (transformList double numbers)  -- Should print [4,8,12,16,20]
```

---

### 💡 Explanation:

* `transformList f = map (f . f)`:

  * This uses function composition `.` to apply `f` twice: `f (f x)`.
  * `map` then applies that to each element of the list.
* For example, if `f = double`, then each number becomes `f (f x)` = `double (double x)`.

---

### ✅ Expected Output:

```
Applying (double . double) to each element:
[4,8,12,16,20]
```



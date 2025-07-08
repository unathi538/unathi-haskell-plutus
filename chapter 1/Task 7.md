HC1T7 - Task 7: Converting Fahrenheit to Celsius



---

### ✅ Haskell Code

```haskell
-- Define a function to convert Fahrenheit to Celsius
fToC :: Float -> Float
fToC f = (f - 32) * 5 / 9

-- Main function to run the program
main :: IO ()
main = do
    putStrLn "Enter temperature in Fahrenheit:"
    input <- getLine
    let fahrenheit = read input :: Float
    let celsius = fToC fahrenheit
    putStrLn $ show fahrenheit ++ "°F is " ++ show celsius ++ "°C"
```

---

### 🧠 Explanation

#### 🔹 Function: `fToC`

```haskell
fToC :: Float -> Float
fToC f = (f - 32) * 5 / 9
```

* `fToC` takes a `Float` (the Fahrenheit temperature).
* Applies the standard conversion formula:
  $(F - 32) \times \frac{5}{9}$

---

#### 🔹 Main Function

```haskell
main :: IO ()
```

* The `main` function handles input/output.

```haskell
putStrLn "Enter temperature in Fahrenheit:"
```

* Prompts the user.

```haskell
input <- getLine
```

* Reads input as a `String`.

```haskell
let fahrenheit = read input :: Float
```

* Converts the string to a floating-point number.

```haskell
let celsius = fToC fahrenheit
```

* Converts the temperature using your function.

```haskell
putStrLn $ show fahrenheit ++ "°F is " ++ show celsius ++ "°C"
```

* Displays the result.

---

### ✅ Example Run:

```
Enter temperature in Fahrenheit:
98.6
98.6°F is 37.0°C
```

---

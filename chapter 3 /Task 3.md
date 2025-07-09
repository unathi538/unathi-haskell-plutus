HC3T3 - Task 3: Convert an RGB color to a hex string using let bindings



---

### ✅ **Haskell Code with Explanation**

```haskell
import Text.Printf (printf)  -- Import printf for string formatting

-- Function to convert an (R, G, B) tuple into a hex color string
rgbToHex :: (Int, Int, Int) -> String
rgbToHex (r, g, b) =
    let hexR = printf "%02X" r  -- Format red component as two-digit hex
        hexG = printf "%02X" g  -- Format green component
        hexB = printf "%02X" b  -- Format blue component
    in hexR ++ hexG ++ hexB     -- Concatenate the hex values into one string

-- Main function to test rgbToHex
main :: IO ()
main = do
    let color1 = rgbToHex (255, 0, 127)   -- Should be "FF007F"
    let color2 = rgbToHex (0, 255, 64)    -- Should be "00FF40"
    
    putStrLn ("rgbToHex (255, 0, 127) = " ++ color1)
    putStrLn ("rgbToHex (0, 255, 64) = " ++ color2)
```

---

### 🧠 Explanation

* **Import**: We import `Text.Printf` for the `printf` function, which allows C-style string formatting.
* **`%02X`**:

  * `%X`: formats the number in **uppercase hexadecimal**.
  * `02`: ensures it is always **2 characters wide**, padding with `0` if necessary (e.g., `7` becomes `07`).
* **`let` bindings** inside the function scope define `hexR`, `hexG`, and `hexB` for each color component.
* The **concatenated result** is returned without a `#` prefix (you could add `"#" ++ hexR ++ hexG ++ hexB` if needed).

---



### 🖨️ Sample Output

```
rgbToHex (255, 0, 127) = FF007F
rgbToHex (0, 255, 64) = 00FF40
```


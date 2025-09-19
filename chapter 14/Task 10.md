HC14T10: Write a cabal test suite for a module that verifies correct behavior of the counts function. 


```haskell
import Data.List (group, sort)

-- Function to count occurrences of each character
counts :: String -> [(Char, Int)]
counts str = map (\xs -> (head xs, length xs)) . group . sort $ str

-- Simple test runner
assertEqual :: (Eq a, Show a) => String -> a -> a -> IO ()
assertEqual label expected actual =
  if expected == actual
    then putStrLn $ "✅ " ++ label ++ " passed."
    else putStrLn $ "❌ " ++ label ++ " failed. Expected: " ++ show expected ++ ", but got: " ++ show actual

-- Main test suite
main :: IO ()
main = do
  putStrLn "Running tests for counts function..."
  assertEqual "Test 1: Empty string" [] (counts "")
  assertEqual "Test 2: Single char" [('a',1)] (counts "a")
  assertEqual "Test 3: Repeated chars" [('a',3),('b',2)] (counts "aaabb")
  assertEqual "Test 4: Mixed chars" [('e',1),('h',1),('l',2),('o',1)] (counts "hello")
  assertEqual "Test 5: With spaces" [(' ',2),('a',3)] (counts "a a a")
```

---


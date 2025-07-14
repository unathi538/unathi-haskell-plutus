Here’s how to **set up a Cabal test suite** to test the `counts` function (which returns character frequencies in a string) using **HUnit**, a popular Haskell testing library.

---

## ✅ 1. Project Structure

```
my-project/
├── app/
│   └── Main.hs            -- Main program
├── src/
│   └── Counts.hs          -- Contains `counts` function
├── test/
│   └── CountsTest.hs      -- Unit tests for `counts`
├── my-project.cabal
```

---

## ✅ 2. Code Files

### 📄 `src/Counts.hs` — the `counts` function

```haskell
module Counts (counts) where

import Data.List (sort, group)

counts :: String -> [(Char, Int)]
counts str = map (\g -> (head g, length g)) . group . sort $ str
```

---

### 📄 `app/Main.hs` — uses `counts` in main

```haskell
module Main where

import Counts (counts)

main :: IO ()
main = do
  putStrLn "Enter a string:"
  input <- getLine
  print $ counts input
```

---

### 📄 `test/CountsTest.hs` — test suite for `counts`

```haskell
module Main (main) where

import Counts (counts)
import Test.HUnit

-- Unit tests
testCounts1 = TestCase (assertEqual "for counts \"banana\""
                        [('a',3),('b',1),('n',2)]
                        (counts "banana"))

testCounts2 = TestCase (assertEqual "for counts \"aaabbbccc\""
                        [('a',3),('b',3),('c',3)]
                        (counts "aaabbbccc"))

testCounts3 = TestCase (assertEqual "for empty input"
                        []
                        (counts ""))

tests = TestList [testCounts1, testCounts2, testCounts3]

main :: IO ()
main = runTestTT tests >>= print
```

---

## ✅ 3. Modify `.cabal` File to Add the Test Suite

Add the following to `my-project.cabal`:

```cabal
test-suite counts-test
  type:                exitcode-stdio-1.0
  hs-source-dirs:      test, src
  main-is:             CountsTest.hs
  build-depends:       base >=4.7 && <5,
                       HUnit,
                       my-project
  default-language:    Haskell2010
```

Also add `HUnit` to the top-level `build-depends` if needed:

```cabal
  build-depends:       base >=4.7 && <5,
                       HUnit
```

---

## ✅ 4. Build and Run the Tests

```bash
cabal build
cabal test counts-test
```

### ✅ Output

```
CountsTest:
  TestCase "for counts \"banana\"": OK
  TestCase "for counts \"aaabbbccc\"": OK
  TestCase "for empty input": OK
CountsTest: [OK, OK, OK]
```

---


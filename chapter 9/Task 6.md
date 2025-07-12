
* `content` (a `String`)
* `likes` (an `Int`)
* `comments` (a list of other `Tweet`s)

---

### ✅ **Full Example**

```haskell
-- Define the recursive Tweet data type
data Tweet = Tweet
  { content  :: String
  , likes    :: Int
  , comments :: [Tweet]
  } deriving Show

-- Example usage in main
main :: IO ()
main = do
    -- A simple tweet with no comments
    let tweet1 = Tweet "Hello, Haskell!" 10 []

    -- A reply (comment) to tweet1
    let reply1 = Tweet "Nice post!" 3 []

    -- Another reply to tweet1
    let reply2 = Tweet "I agree!" 5 []

    -- A tweet with comments
    let tweet2 = Tweet "Learning recursion is fun!" 20 [reply1, reply2]

    putStrLn "Tweet 1 (no comments):"
    print tweet1

    putStrLn "\nTweet 2 (with comments):"
    print tweet2
```

---

### 🔍 Explanation

* `Tweet` is a recursive data type because its `comments` field contains a list of `Tweet`s.
* The `deriving Show` allows you to print the tweet structure.
* In `main`, we construct nested tweets to simulate replies/comments.

---

### 💡 Sample Output

```
Tweet 1 (no comments):
Tweet {content = "Hello, Haskell!", likes = 10, comments = []}

Tweet 2 (with comments):
Tweet {content = "Learning recursion is fun!", likes = 20, comments = [Tweet {content = "Nice post!", likes = 3, comments = []},Tweet {content = "I agree!", likes = 5, comments = []}]}
```


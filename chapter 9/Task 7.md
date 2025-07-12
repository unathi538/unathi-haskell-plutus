

* Defines the recursive `Tweet` data type,
* Implements the `engagement` function to sum likes and recursively count the engagement of all comments,
* Includes a `main` function that builds a tweet thread and prints the total engagement.

---

### ✅ **Full Example**

```haskell
-- Define the recursive Tweet data type
data Tweet = Tweet
  { content  :: String
  , likes    :: Int
  , comments :: [Tweet]
  } deriving Show

-- Define the engagement function
engagement :: Tweet -> Int
engagement (Tweet _ likes comments) =
  likes + sum (map engagement comments)

-- Example usage in main
main :: IO ()
main = do
    -- Base tweet
    let tweet1 = Tweet "Functional programming rocks!" 10 []

    -- Replies to tweet1
    let reply1 = Tweet "Totally agree!" 4 []
    let reply2 = Tweet "I'm still confused though." 2 []

    -- A nested reply to reply1
    let reply1a = Tweet "Don't worry, it gets easier." 3 []

    -- Adding nested reply to reply1
    let reply1WithNested = reply1 { comments = [reply1a] }

    -- Tweet with multiple levels of comments
    let mainTweet = Tweet "Learning Haskell!" 15 [tweet1, reply1WithNested, reply2]

    putStrLn "Main Tweet Thread:"
    print mainTweet

    let totalEngagement = engagement mainTweet
    putStrLn $ "\nTotal Engagement: " ++ show totalEngagement
```

---

### 🔍 Explanation

* `engagement`:

  * Takes a `Tweet` and returns its likes plus the recursive sum of engagements from its comments.
* `map engagement comments` applies the function to each comment.
* `sum` aggregates the engagement from all replies.

---

### 💡 Sample Output

```
Main Tweet Thread:
Tweet {content = "Learning Haskell!", likes = 15, comments = [Tweet {content = "Functional programming rocks!", likes = 10, comments = []},Tweet {content = "Totally agree!", likes = 4, comments = [Tweet {content = "Don't worry, it gets easier.", likes = 3, comments = []}]},Tweet {content = "I'm still confused though.", likes = 2, comments = []}]}

Total Engagement: 34
```


HC1T4 - Task 4: Composing a Function to Process Player Data



```haskell
import Data.List (sortBy)
import Data.Ord (comparing)

-- Type synonym for clarity
type Player = (String, Int)

-- Extract player names from a list of (name, score) tuples
extractPlayers :: [Player] -> [String]
extractPlayers players = [name | (name, _) <- players]

-- Sort players by score in descending order
sortByScore :: [Player] -> [Player]
sortByScore = sortBy (flip (comparing snd))

-- Return the top three players
topThree :: [Player] -> [Player]
topThree = take 3

-- Compose the above functions
getTopThreePlayers :: [Player] -> [String]
getTopThreePlayers = extractPlayers . topThree . sortByScore

-- Main function to test the logic
main :: IO ()
main = do
    let players = [("Alice", 90), ("Bob", 75), ("Charlie", 95), ("Diana", 88), ("Eve", 70)]
    putStrLn "All Players:"
    print players

    putStrLn "\nTop Three Player Names:"
    print (getTopThreePlayers players)
```

---

### Explanation:

* `extractPlayers`: Gets only the names from `(name, score)` tuples.
* `sortByScore`: Sorts players based on score (highest to lowest).
* `topThree`: Takes the top 3 players from the sorted list.
* `getTopThreePlayers`: Composes all three into one clean pipeline.

### Sample Output:

```
All Players:
[("Alice",90),("Bob",75),("Charlie",95),("Diana",88),("Eve",70)]

Top Three Player Names:
["Charlie","Alice","Diana"]
```



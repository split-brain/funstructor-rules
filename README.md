# funstructor

Turn-based multiplayer game designed for the geek audience.

## Game

Two players start the game.

There is a common deck of cards and at the start of the game
each player draws 6 cards.
Also, each player assigned a random
simple clojure function implementation but the
opponent doesn't know what the function is.

Each turn each player draw two cards, and third card is shown to both players, 50/50 random choose its owner.

Both players have their own board where they are constructing function. Both boards are visible to both players.

At the start of the game a board contains just one gap and your goal to build your function.

There are 60 seconds time limit for playing cards.

## Future gameplay ideas

- **Roles**/**Classes** - same as durations but are permanent during game.

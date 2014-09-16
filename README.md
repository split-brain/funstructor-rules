# funstructor

Turn-based multiplayer game designed for the geek audience.

## Game

Two players start the game.

There is a common deck of cards and at the start of the game
each player draws 6 cards. Also, each player assigned a random
simple clojure function implementation but the
opponent doesn't know what the function is.

Both players have their own board where they are constructing function.
Both boards are visible to both players.

At the start of the game a board contains just one symbol `F`
There are rules, how that symbol could be expanded to the function.

## Rules

Rules based on a simple grammar contain
*terminal* and *non-terminal* symbols.

- **Non-terminal** symbols are bold and can be expanded using grammar.
- `Terminal` symbols can't be expanded.

1. **F** -> `(` `defn` `<id>` `[` `<id>`* `]` **FORM** `)`
2. **FORM** -> `(` `<id>` **ARG*** `)`
3. **ARG** -> `<id>` | `<num>` | **FORM**

## Cards

In general playing cards can be divided into two types: constructive and
destructive. Constructive cards are used to build on your own function.
Destructive cards are used to destroy or affect in some nasty way
elements in yours or your opponent's function or hand.

* **Constructive**
  - LPAREN `(`
  - RPAREN `)`
  - DEFN `defn`
  - `<id>` (after playing this card you can type the name of id)
  - LSQUARE `[`
  - RSQUARE `]`
  - `<num>` (after playing this card you can type the int number)
  - `[*]` (expand non-terminal using the rule)
  - `[#]` (stop multielement)

* **Destructive**
  - Collapse (fold) non-terminal
  - Delete terminal
  - Delete non-terminal
  - Delete card in hand
  - Rename `<id>`
  - Replace `<num>`
  - Reverse all parentheses in hand


## Example

Consider the following function

``` clojure
(defn even? [x]
  (zero? (mod? x 2)))
```

Starting with non-terminal **F** we could build the
function using following rules step-by-step

- **F**
  - Expand `[*]` **F**
- `(` `defn` `<id>` `[` `<id>`* `]` **FORM** `)`
  - LPAREN
  - DEFN
  - `<id>`:even?
  - LSQUARE
  - `<id>`:x
  - RSQUARE
  - RPAREN
- `(` `defn` `even?` `[` `x` `<id>*` `]` **FORM** `)`
  - `[#]` Stop multielement `<id>*`
- `(` `defn` `even?` `[` `x` `]` **FORM** `)`
  - `[*]` Expand **FORM**
- `(` `defn` `even?` `[` `x` `]` `(` `<id>` **ARG***`)` `)`
  - `<id>`:zero?
- `(` `defn` `even?` `[` `x` `]` `(` `zero?` **ARG***`)` `)`
  - Expand `[*]` **ARG** -> **FORM**
- `(` `defn` `even?` `[` `x` `]` `(` `zero?` **FORM** **ARG***`)` `)`
  - `[#]` Stop multielement **ARG***
- `(` `defn` `even?` `[` `x` `]` `(` `zero?` **FORM** `)` `)`
  - Expand `[*]` **FORM**
- `(` `defn` `even?` `[` `x` `]` `(` `zero?` `(` `<id>` **ARG*** `)` `)` `)`
  - `<id>`:mod
- `(` `defn` `even?` `[` `x` `]` `(` `zero?` `(` `mod` **ARG*** `)` `)` `)`
  - Expand `[*]` **ARG** -> `<id>`
- `(` `defn` `even?` `[` `x` `]` `(` `zero?` `(` `mod` `<id>` **ARG*** `)` `)` `)`
  - Expand `[*]` **ARG** -> `<num>`
- `(` `defn` `even?` `[` `x` `]` `(` `zero?` `(` `mod` `<id>` `<num>` **ARG*** `)` `)` `)`
  - `[#]` Stop multielement **ARG***
- `(` `defn` `even?` `[` `x` `]` `(` `zero?` `(` `mod` `<id>` `<num>` `)` `)` `)`
  - `<id>`:x
  - `<num>`:2
- `(` `defn` `even?` `[` `x` `]` `(` `zero?` `(` `mod` `x` `2` `)` `)` `)`

Construction is done!


## Gameplay ideas

- **Abilities** - cards that affect player's game process in some way.
                  They are placed near player and can be viewed by his
                  opponent (and of course destructive cards can be used
                  on them). Example: LL3-parser - each turn player takes
                  3 cards (instead of 2), chooses 2 to keep and puts the
                  the other one back on the deck, face down.

- **Roles**/**Classes** - same as abilities but are permanent during game.

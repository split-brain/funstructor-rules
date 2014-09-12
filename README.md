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

* **Terminals**
  - LPAREN `(`
  - RPAREN `)`
  - DEFN `defn`
  - <ID> `<id>` (after playing this card you can type the name of id)
  - LSQUARE `[`
  - RSQUARE `]`
  - <NUM> `<num>` (after playing this card you can type the int number)
* **Non-terminal**
  - `[*]` (expand non-terminal using the rule)
  - `[-]` (collapse non-terminal)
  - `[.]` (delete terminal)
  - `[X]` (delete non-terminal)
  - `[#]` (stop multielement)

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
  - <ID>:even?
  - LSQUARE
  - <ID>:x
  - RSQUARE
  - RPAREN
- `(` `defn` `even?` `[` `x` `<id>*` `]` **FORM** `)`
  - `[#]` Stop multielement `<id>*`
- `(` `defn` `even?` `[` `x` `]` **FORM** `)`
  - `[*]` Expand **FORM**
- `(` `defn` `even?` `[` `x` `]` `(` `<id>` **ARG***`)` `)`
  - <ID>:zero?
- `(` `defn` `even?` `[` `x` `]` `(` `zero?` **ARG***`)` `)`
  - Expand `[*]` **ARG** -> **FORM**
- `(` `defn` `even?` `[` `x` `]` `(` `zero?` **FORM** **ARG***`)` `)`
  - `[#]` Stop multielement **ARG***
- `(` `defn` `even?` `[` `x` `]` `(` `zero?` **FORM** `)` `)`
  - Expand `[*]` **FORM**
- `(` `defn` `even?` `[` `x` `]` `(` `zero?` `(` `<id>` **ARG*** `)` `)` `)`
  - <ID>:mod
- `(` `defn` `even?` `[` `x` `]` `(` `zero?` `(` `mod` **ARG*** `)` `)` `)`
  - Expand `[*]` **ARG** -> `<id>`
- `(` `defn` `even?` `[` `x` `]` `(` `zero?` `(` `mod` `<id>` **ARG*** `)` `)` `)`
  - Expand `[*]` **ARG** -> `<num>`
- `(` `defn` `even?` `[` `x` `]` `(` `zero?` `(` `mod` `<id>` `<num>` **ARG*** `)` `)` `)`
  - `[#]` Stop multielement **ARG***
- `(` `defn` `even?` `[` `x` `]` `(` `zero?` `(` `mod` `<id>` `<num>` `)` `)` `)`
  - <ID>:x
  - <NUM>:2
- `(` `defn` `even?` `[` `x` `]` `(` `zero?` `(` `mod` `x` `2` `)` `)` `)`

Construction is done!

## Destruction

Important part of the game that you not only can build your own function,
you can also destroy some elements in your opponent's function.

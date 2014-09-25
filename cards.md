# List of cards

Card have its name and prefix, prefix describes category of card.

- **Terminal** Just use terminal on empty terminal space.
- **Duration** Card put on board add some effect applied to your or opponent's future actions for few turns
- **Mutator** Change the structure and content of the function
- **Action** Perform some action based on card description
- **Hidden** Activate hidden card
- **Special** Rare cards, almost always hard to use, but give a real benefit

</hr>

# First Iteration Cards (TODO)


### Terminal

01. **Terminal: LPAREN**
02. **Terminal: RPAREN**
03. **Terminal: LSQUARE**
04. **Terminal: RSQUARE**
07. **Terminal: ID**
08. **Terminal: NUM**

### Mutator

01. **Mutator: Left Gap** (put gap to the leftmost position)
02. **Mutator: Right Gap** (put gap to the rightmost position)
03. **Mutator: Position Gap** (put gap at the specific position)
04. **Mutator: Left Trim** (remove all gaps from the left side)
05. **Mutator: Right Trim** (remove all gaps from the right side)
06. **Mutator: Trim** (remove all gaps from the left and right side)
07. **Mutator: Cleanup** (remove gaps from the opponent's funstruct)
08. **Mutator: Terminal Shot** (delete specific terminal)
09. **Mutator: Sleep Shot** (delete terminal)
10. **Mutator: Embargo** (select your terminal and destroy all these terminals from game)
11. **Mutator: Refactoring** (move terminal to specific position)
12. **Mutator: Gap Shot** (delete gap)

### Action

01. **Action: Thief v1.0** (steal card from opponent hand)
02. **Action: Thief v2.0** (steal card from opponent board)
03. **Action: Discard v1.0** (opponent discard random card)
04. **Action: Discard v2.0** (discard one of your cards, opponent discard all the same cards)
05. **Action: Discard v3.0** (discard one of your cards, opponent discard all cards of the same type)
06. **Action: Discard v4.0** (opponent discard all cards)
07. **Action: Equality v1.0** (you and your opponent discard all cards from hand and take 5 from deck)
08. **Action: Equality v2.0** (you and your opponent discard all cards from board)
09. **Action: Equality v3.0** (you take cards until you'll have the same as your opponent)
10. **Action: Refresh** (discard all your cards and take the same amount from deck)
11. **Action: REPL** (three test inputs for opponent's function)
12. **Action: LL(1)** (look top three cards at the deck and choose one)
13. **Action: Greedy** (get cards upto your maximum)
14. **Action: Spy** (next card could be used on opponent's funstruct)

### Duration

01. **Duration: Memory** (your maximum number of cards +10 for 10 turns)
02. **Duration: Scanner** (able to see opponent's cards for 5 turns)
03. **Duration: Smartparens Mode** (automatically close paren when you open it for 5 turns)
04. **Duration: Discard Curse** (lasts 5 turns, each turn opponent forced to discard random card)
05. **Duration: Terminal Curse** (lasts 3 turns, opponent can't place terminals)
06. **Duration: Action Curse** (lasts 3 turns, opponent can't use actions)
07. **Duration: Mutator Curse** (lasts 3 turns, opponent can't use mutators)
08. **Duration: Duration Curse** (lasts 3 turns, opponent can't use duration cards)
09. **Duration: Hidden Curse** (lasts 3 turns, opponent can't use hidden cards)
10. **Duration: Special Curse** (lasts 5 turns, opponent can't use special cards)
11. **Duration: Thief v3.0** (lasts 3 turns, each turn opponent plays a card, you get its copy in your hand)
12. **Duration: Luck v1.0** (lasts 3 turns, your chances to get third card become 75%)
13. **Duration: Luck v2.0** (lasts 3 turns, your chances to get third card becomes 100%)

### Hidden

01. **Hidden: Redirrect** (next action, hidden or duration card change its owner)
02. **Hidden: Shot** (next terminal are played by opponent are deleted)
03. **Hidden: Annihilation** (next card played by opponent are take no effect)
04. **Hidden: Copy** (next card plated by opponent copied to your hand)

;; TODO more hiddens

### Special

01. **Special: Virus** (virus moves inside your function each turn *forever* until you use Virus Kill or Virus Cure,
virus blocks place for terminal)
02. **Special: Hot Swap** (swap function with your opponent)
03. **Special: Duplicate** (select terminal on board and get 5 copies of it)
04. **Special: Rainbow Nuke** (you have 5 turns, you musy use cards of all types terminal, mutator, duration, action and hidden. If you used cards of all types destroy all terminals from your opponent's function)
04. **Special: Duel** (put left paren, square or curly, opponent forced to close it with right paren,
then you forced to put left paren, who wins get all parens as terminals back to hand)

# Future Releases/Outdated (TODO revisit)

05. **Terminal: LCURLY**
06. **Terminal: RCURLY**

05. **Mutator: ID->NUM** (replace id on board to num)
06. **Mutator: Shuffle** (shuffles all terminals of function)
07. **Mutator: NUM->ID** (replace num on board to id)
08. **Mutator: Really?** (add question mark `?` to every id)
09. **Mutator: Mutable!** (add exclamation mark `!` to every id)
10. **Mutator: Virus Kill** (remove virus from function, see special)
11. **Mutator: Virus Migrate** (virus moves across your and your opponent function)
12. **Mutator: Virus Cure** (replace virus with terminal)
14. **Mutator: Pain** (remove random terminal from your and opponent's function)
16. **Mutator: Rehydration** (fill all available terminals you have in your hand, discard others) 

11. **Action: Reverse Time** (discard opponent last actions)
14. **Action: Reveal** (all opponent active hidden actions are discarded)
15. **Action: Scheme Attack** (all opponent's square brackets in hand are transformed to parenheses)

01. **Duration: Emoji Generation** (your parens transformed to smiles for 5 turns,
no need to remove them, just visual effect)
05. **Duration: Friends** (lasts 5 turns, if you put terminal automatically fill both neighbour terminals) (outdated)
02. **Duration: Speed** (last 5 turns, each player is forced to take a move in 15 seconds)

02. **Hidden: Postponed Terminal** (use this card and one terminal, on next turn you able to play this terminal for free)

03. **Special: Bytecode** (replace function with its bytecode for 10 turns, though you can construct bytecode)
04. **Special: ASCII** (replace all symbols to ascii values for 10 turns, all terminals are numbers)
05. **Special: Hot Swap** (swap function with your opponent)
06. **Special: Duplicate** (select terminal on board and get 5 copies of it)
07. **Special: Rainbow Nuke** (you have 5 turns, you must use cards of all types terminal, mutator, duration, action and hidden. If you used cards of all types destroy all terminals from your opponent's function)

> Powered by brainstorm

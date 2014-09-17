# List of cards

Card have its name and prefix, prefix describes category of card.

- **Terminal** Just use terminal on empty terminal space.
- **Duration** Card put on board add some effect applied to your or opponent's future actions for few turns
- **Mutator** Change the structure and content of the function
- **Action** Perform some action based on card description
- **Hidden** Activate hidden card
- **Special** Rare cards, almost always hard to use, but give a real benefit

</hr>

01. **Terminal: LPAREN**
02. **Terminal: RPAREN**
03. **Terminal: LSQUARE**
04. **Terminal: RSQUARE**
05. **Terminal: LCURLY**
06. **Terminal: RCURLY**
07. **Terminal: ID**
08. **Terminal: NUM**
09. **Terminal: defn**
10. **Terminal: nil**

01. **Mutator: Expand** (replace non-terminal with rule)
02. **Mutator: Collapse** (fold empty rule to its non-terminal)
03. **Mutator: Shot** (delete terminal)
04. **Mutator: Swap S-Exps** (transpose two S-Expressions)
05. **Mutator: ID->NUM** (replace id on board to num)
06. **Mutator: Shuffle** (shuffles all terminals of function)
07. **Mutator: NUM->ID** (replace num on board to id)
08. **Mutator: Really?** (add question mark `?` to every id)
09. **Mutator: Mutable!** (add exclamation mark `!` to every id)
10. **Mutator: Virus Kill** (remove virus from function, see special)
11. **Mutator: Virus Migrate** (virus moves across your and your opponent function)
12. **Mutator: Virus Cure** (replace virus with terminal)
13. **Mutator: Refactoring** (shuffle toplevel S-Exps as you want)
14. **Mutator: Pain** (remove random terminal from your and opponent's function)
15. **Mutator: Embargo** (select your terminal and destroy all these terminals from game)
16. **Mutator: Rehydration** (fill all available terminals you have in your hand, discard others) 

01. **Action: Thief v1.0** (steal card from opponent hand)
02. **Action: Thief v2.0** (steal card from opponent board)
03. **Action: Discard v1.0** (opponent discard random card)
04. **Action: Duel** (put left paren, square or curly, opponent forced to close it with right paren,
then you forced to put left paren, who wins get all parens as terminals back to hand)
05. **Action: Equality v1.0** (you and your opponent discard all cards from hand and take 5 from deck)
06. **Action: Equality v2.0** (you and your opponent discard all cards from board)
07. **Action: Equality v3.0** (you take cards until you'll have the same as your opponent)
08. **Action: Refresh** (discard all your cards and take the same amount from deck)
09. **Action: REPL** (three test inputs for opponent's function)
10. **Action: LL(1)** (look top three cards at the deck and choose one)
11. **Action: Reverse Time** (discard opponent last actions)
12. **Action: Discard v2.0** (discard one of your cards, opponent discard all the same cards)
13. **Action: Discard v3.0** (discard one of your cards, opponent discard all cards of the same type)
14. **Action: Reveal** (all opponent active hidden actions are discarded)

01. **Duration: Emoji Generation** (your parens transformed to smiles for 5 turns,
no need to remove them, just visual effect)
02. **Duration: Memory** (your maximum number of cards +10 for 10 turns)
03. **Duration: Scanner** (able to see opponent's cards for 5 turns)
04. **Duration: Smartparens Mode** (automatically close paren when you open it for 5 turns)
05. **Duration: Friends** (lasts 5 turns, if you put terminal automatically fill both neighbour terminals)
06. **Duration: Discard Curse** (lasts 5 turns, each turn opponent forced to discard random card)
07. **Duration: Terminal Curse** (lasts 5 turns, opponent can't place terminals)
08. **Duration: Action Curse** (lasts 5 turns, opponent can't use actions)
09. **Duration: Mutator Curse** (lasts 5 turns, opponent can't use mutators)
10. **Duration: Duration Curse** (lasts 5 turns, opponent can't use duration cards)
11. **Duration: Hidden Curse** (lasts 5 turns, opponent can't use hidden cards)
12. **Duration: Special Curse** (lasts 5 turns, opponent can't use special cards)
13. **Duration: Thief v3.0** (lasts 5 turns, each turn opponent plays a card, you get its copy in your hand)
14. **Duration: Double** (lasts 5 turns, each turn you can use two cards)
15. **Duration: Repeat** (lasts 5 turns, each turn opponent forced to use card of the same type as you on the previous)
16. **Duration: Luck v1.0** (lasts 3 turns, your chances to get third card become 75%)
17. **Duration: Luck v2.0** (lasts 3 turns, your chances to get third card becomes 100%)

01. **Hidden: Redirrect** (action or curse applied to you by opponent redirrected back to him)
02. **Hidden: Postponed Terminal** (use this card and one terminal, on next turn you able to play this terminal for free)

01. **Special: Paredit God** (use any paredit function for the code)
02. **Special: Virus** (virus moves inside your function each turn *forever* until you use Virus Kill or Virus Cure,
virus blocks place for terminal)
03. **Special: Bytecode** (replace function with its bytecode for 10 turns, though you can construct bytecode)
04. **Special: ASCII** (replace all symbols to ascii values for 10 turns, all terminals are numbers)
05. **Special: Hot Swap** (swap function with your opponent)
06. **Special: Duplicate** (select terminal on board and get 5 copies of it)
07. **Special: Rainbow Nuke** (you have 5 turns, you musy use cards of all types terminal, mutator, duration, action and hidden. If you used cards of all types destroy all terminals from your opponent's function)

> Powered by brainstorm

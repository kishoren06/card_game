# Card Game - War

A simple command-line implementation of the classic card game **War** in Python.

## Description

Two players draw cards from a shuffled deck in each round. The player with the higher-value card wins the round and scores a point. The player with the most points at the end of the game is declared the winner.

### Game Rules
- Each round, both players draw one card from the deck
- The player with the higher card value wins the round
- If values are equal, the player with the higher suit wins (spades > hearts > diamonds > clubs)
- The game continues until the deck is exhausted
- The player with the most round wins is the overall winner

## Project Structure

```
kishoren06/card_game/
├── README.md          # Project documentation
├── card_game.py       # Main game implementation
└── code               # Original game code (archived)
```

## How to Run

### Prerequisites
- Python 3.6 or higher

### Installation & Execution

1. Clone the repository:
```bash
git clone https://github.com/kishoren06/card_game.git
cd card_game
```

2. Run the game:
```bash
python card_game.py
```

3. Follow the prompts:
   - Enter Player 1's name
   - Enter Player 2's name
   - Press ENTER to play each round
   - Press `q` to quit early

## Example Output

```
==================================================
Welcome to War!
Alice vs Bob
==================================================

Press ENTER to play round (or 'q' to quit): 

Alice drew: 7 of spades
Bob drew: 5 of hearts
→ Alice wins this round!
Score: Alice 1 - 0 Bob

Press ENTER to play round (or 'q' to quit): 

Alice drew: King of diamonds
Bob drew: Jack of clubs
→ Alice wins this round!
Score: Alice 2 - 0 Bob

Press ENTER to play round (or 'q' to quit): 

Bob drew: Ace of spades
Alice drew: 9 of hearts
→ Bob wins this round!
Score: Alice 2 - 1 Bob

Press ENTER to play round (or 'q' to quit): q

==================================================
War is over!
==================================================
Rounds played: 3
Final Score: Alice 2 - 1 Bob
🎉 Alice wins the war! 🎉
==================================================
```

## Code Features

- **Card Class**: Represents individual cards with value and suit
  - Implements comparison operators (`__lt__`, `__gt__`) for card ranking
  - String representation shows card name and suit

- **Deck Class**: Creates and manages a shuffled 52-card deck
  - Automatic deck generation with all combinations of values and suits
  - `draw_card()` method removes and returns the next card
  - `__len__()` method tracks remaining cards

- **Player Class**: Tracks player name and win count
  - Maintains round wins throughout the game
  - String representation for easy display

- **Game Class**: Controls game flow and user interaction
  - Manages two players and game state
  - `play_round()` determines winner of each round
  - `play_game()` executes main game loop
  - `end_game()` displays final results with formatted output

## Key Optimizations

### Performance
- List comprehension for deck initialization (faster than nested loops)
- Efficient card comparison using tuple-like logic
- Proper use of `pop()` for O(1) card removal

### Code Quality
- Simplified comparison logic (removed nested if-else chains)
- F-strings for modern, readable string formatting
- Comprehensive docstrings for all classes and methods
- Proper naming conventions (descriptive variable names)

### Readability
- Better code organization with logical method grouping
- Cleaner string formatting without line breaks
- Removed redundant variable assignments
- Professional entry point with `if __name__ == "__main__"` guard

### User Experience
- Visual separators and formatted output
- Clear game status and score tracking
- Helpful prompts and messages
- Emoji indicators for game results
- Round counter for tracking game length

## File Descriptions

| File | Purpose |
|------|---------|
| `README.md` | Complete project documentation with usage examples |
| `card_game.py` | Optimized main game implementation |
| `code` | Original game code (preserved for reference) |

## Classes and Methods

### Card
- `__init__(value, suit)` - Initialize a card
- `__lt__(other)` - Compare if card is less than another
- `__gt__(other)` - Compare if card is greater than another
- `__repr__()` - String representation of card

### Deck
- `__init__()` - Create shuffled 52-card deck
- `draw_card()` - Draw and remove a card
- `__len__()` - Get number of remaining cards

### Player
- `__init__(name)` - Initialize player with name
- `wins` - Attribute to track round wins

### Game
- `__init__()` - Initialize game with two players
- `play_round(card1, card2)` - Determine round winner
- `play_game()` - Execute main game loop
- `end_game()` - Display final results

## Future Enhancements

- Support for more than 2 players (multiplayer mode)
- Configurable deck size and card values
- Game statistics and win history
- GUI interface using tkinter or pygame
- Unit tests and game simulation
- AI opponent mode
- Difficulty levels for AI

## Contributing

Feel free to fork this repository and submit pull requests for any improvements!

## License

This project is open source and available for educational purposes.

---

**Repository**: https://github.com/kishoren06/card_game  
**Created by**: kishoren06  
**Last Updated**: 2026-07-24

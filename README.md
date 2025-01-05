# Red-Seven-Game
The Solo Red game is a solitaire variant inspired by the card game Red7. In this game, players aim to keep their palettes "winning" under an ever-changing set of rules dictated by a card on the canvas.
## Components
### Cards:
- Each card is represented by a color (Red, Orange, Blue, Indigo, Violet) and a number (1-7)
- Colors represent a set of rules, while numbers dictate values
- An example of a card in the game would be `O5`, meaning the card is orange and has a value of five
### Layout:
- **Deck**: Cards are drawn from here after the player plays a card to the palette or when the game starts
- **Palette**: A group of cards the player will be interacting with
- **Canvas**: A card whose color determines the current rules of the game
- **Hand**: Cards available for the player to play
### Color Rules:
These rules determine what palette is currently winning the game.
#### Red:
The palette with the highest card wins.
- Note: if the numbers are equal, we use rainbow order of colors to break the tie (Red > Orange > etc)
#### Orange:
The palette with the most of a single number wins.
#### Blue:
The palette with the most cards of different colors wins.
#### Indigo:
The palette with the cards that form the longest run wins.
- Note: runs are considered as consecutive numbers like `R1`, `B2`, `V3`
- They do not have to be in order
#### Violet
The palette with the most cards below the value of 4 wins.
#### Tie Breaker
If there is a tie with any of these rules, apply the red rule to the cards contributing to the tie.
### Game Modes:
#### Basic
The game plays as described
#### Advanced
The following rules have changed: the player can only draw one card from the deck when playing to a palette. If the player plays a card to canvas and the canvas card's number is greater than the number of cards in the winning palette, then the player can draw a boosted draw of an additional card the next time they play to a palette (but only once per boost given).
## Mechanics
### Setup:
- Palettes are created by drawing one card for each palette from the deck
- The canvas starts with a special red card (The canvas will always start red)
- The player's hand is filled by drawing cards to the deck
### Actions:
- Play a card to a losing palette to make it win
- Play a card to the canvas to change the rules
### Progression:
- After playing to a palette, the player will draw a card to their hand
- The game will end if:
  - Win: The player plays all the cards in their hand and deck and the last card played makes the palette win
    - Note: The last card of the game must be played to a palette and that palette become the winning palette
  - Lose: The player plays to a palette and it does not become the winning palette
    - Note: Playing to the canvas cannot make the game lose
## Starting the Game
Run the program in your terminal with the following command:  
java -jar RedSolo.jar [Game mode] [Number of Palettes] [Size of Hand]  
**Game modes**: Basic, Advanced  
**Number of Palettes**: Must be greater than 1  
**Hand Size**: Number of cards in your hand during the game  
**Default values**: `Basic 4 7`  
If any of the integer values are not entered correctly, the game will default to those values  

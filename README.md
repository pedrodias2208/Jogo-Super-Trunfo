Super Trunfo - Football Legends

A terminal-based Super Trunfo (Top Trumps) card game built in Python, featuring football player cards (legends and current stars) with FIFA-style attributes. Supports two-player matches or matches against the computer, with 3 difficulty levels.

🎯 What it does
Implements the classic Super Trunfo rules: each player picks an attribute from their top card and compares it against the opponent's — whoever has the higher value wins the round and takes both cards
Deck of 20 football player cards (legends like Pelé and Zidane, and current stars like Mbappé and Haaland), each with 7 attributes: Overall, Pace, Finishing, Passing, Dribbling, Defending, and Physical
Shuffles and evenly splits the deck between the two players at the start of the match
Two game modes:
Player vs Player (PvP): two human players taking turns on the same terminal
Player vs Computer (PvE): with 3 AI difficulty levels
AI with 3 difficulty levels:
Easy: picks a random attribute
Medium: picks the second-best attribute on its own card
Hard: always picks the best attribute on its own card
Terminal interface with colors (ANSI), cards rendered as boxes, and ASCII art on the main menu
Handles ties (no cards change hands) and ends the game once one player runs out of cards
🛠️ Technologies used
Pure Python 3 — no external libraries
Standard library modules: random (shuffling the deck and easy-mode AI), os (clearing the terminal between rounds), time (dramatic pauses between actions)
ANSI escape codes for terminal colors
🚀 How to run
bash
# Clone the repository
git clone https://github.com/your-username/repo-name.git
cd repo-name

# No external dependencies needed, just run:
python super_trunfo.py

💡 Works best in terminals that support ANSI colors and emojis (most modern terminals on Linux/Mac; on Windows, the modern CMD and Windows Terminal work well).

💡 How it works (technical summary)
The 20 cards are shuffled with random.shuffle and split evenly between the two players (using lists as queues)
Each round, the current player sees their top card and picks an attribute (1 to 7) to compete with
In PvE mode, the AI picks the attribute based on the selected difficulty, scanning the 7 attributes on its own card to find the highest, second-highest, or picking randomly
The values for the chosen attribute are compared between both top cards; whoever has the higher value wins and takes both cards (added to the back of their deck); on a tie, each player keeps their own card
Cards are handled as queues: pop(0) removes the top card and append adds it back to the bottom of the deck
Turns alternate until one deck runs out — the other player wins
📌 Possible future improvements
Add more cards / support importing cards from an external file (CSV or JSON)
Save match history or win statistics
Port the interface to a graphical version (e.g. Pygame) or the web
Validate user input (currently int(input(...)) crashes on invalid input)
📄 License

This project is licensed under the MIT License.

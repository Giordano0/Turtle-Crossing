# 🐢 Turtle Crossing

A Frogger-style game built with Python and the Turtle graphics library. Guide your turtle across a busy road without getting hit by cars!

## 🎮 Gameplay

- Control a turtle starting at the bottom of the screen
- Press **W** to move up
- Avoid the incoming cars moving from right to left
- Reach the top of the screen to advance to the next level
- Each level increases the speed of the cars
- The game ends when a car hits the turtle

## 📁 Project Structure

```
TurtleCrossing/
│
├── main.py          # Game loop and screen setup
├── player.py        # Player (turtle) movement and logic
├── car_manager.py   # Car creation, movement, and speed management
├── scoreboard.py    # Level display and game over screen
```

## 🧩 How It Works

### `player.py`
The `Player` class extends `Turtle`. It spawns at the bottom center of the screen `(0, -280)`, faces upward, and moves forward by 10 pixels each time **W** is pressed. It also detects when the finish line at `y = 280` is reached and resets to the starting position.

### `car_manager.py`
The `CarManager` class handles all cars on screen. Cars are created randomly (1 in 6 chance per game cycle) as colored squares on the right side of the screen, moving left at increasing speed. Every time the player reaches the top, `level_up()` is called and the speed increases by 10.

### `scoreboard.py`
The `Scoreboard` class extends `Turtle` and displays the current level in the top-left corner. It updates every time the player levels up and shows a "GAME OVER" message in the center of the screen when the game ends.

### `main.py`
Sets up the screen and runs the main game loop. Every cycle it:
1. Creates and moves cars
2. Checks if the player reached the finish line (level up)
3. Checks for collisions between the player and any car (game over)

## ▶️ How to Run

Make sure you have Python installed, then run:

```bash
python main.py
```

No external libraries required — only the built-in `turtle` module.

## 🕹️ Controls

| Key | Action |
|-----|--------|
| W   | Move up |

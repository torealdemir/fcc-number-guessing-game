# Number Guessing Game

A simple and interactive number-guessing game built with **Bash** and **PostgreSQL**. The game generates a random number between 1 and 1000, and users are tasked with guessing it. It tracks users based on their usernames and maintains statistics, including the total number of games played and the fewest guesses required to win. The game is designed to welcome both new and returning users, updating their statistics in a PostgreSQL database after each game.

The project features random number generation, user tracking, and input validation to ensure smooth gameplay. Users are guided with hints if their guesses are too high or too low, and non-integer inputs are handled gracefully. The game is backed by a PostgreSQL database, which stores user details and gameplay statistics.

## Setup and Installation

To set up and run the game, follow these steps:

1. **Clone the Repository**:
   ```bash
   git clone <repository-url>
   cd number_guessing_game

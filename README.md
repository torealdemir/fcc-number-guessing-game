Number Guessing Game
A simple number-guessing game built with Bash and PostgreSQL. Users guess a randomly generated number between 1 and 1000, with the game tracking statistics such as the total number of games played and the fewest guesses needed to win. The game welcomes both new and returning users and updates their statistics in a PostgreSQL database.

Features
Random Number Generation: The game generates a random number between 1 and 1000 for the user to guess.
User Tracking:
New users are welcomed and added to the database.
Returning users are greeted with their game history.
Statistics:
Tracks the total number of games played by each user.
Stores the best game (fewest guesses).
Input Validation: Ensures user input is an integer before proceeding.
Database Integration: Stores user data and game statistics in a PostgreSQL database.
Setup and Installation
Clone the Repository:

bash
Kodu kopyala
git clone <repository-url>
cd number_guessing_game
Database Setup:

Connect to PostgreSQL:
bash
Kodu kopyala
psql --username=freecodecamp --dbname=postgres
Create the number_guess database and its table:
sql
Kodu kopyala
CREATE DATABASE number_guess;
\c number_guess

CREATE TABLE users (
    user_id SERIAL PRIMARY KEY,
    username VARCHAR(22) UNIQUE NOT NULL,
    games_played INT DEFAULT 0,
    best_game INT
);
Exit PostgreSQL:
bash
Kodu kopyala
\q
Make the Script Executable:

bash
Kodu kopyala
chmod +x number_guess.sh
Run the Game:

bash
Kodu kopyala
./number_guess.sh
How to Play
Run the script and enter your username when prompted:
mathematica
Kodu kopyala
Enter your username:
If you're a new user, you'll be welcomed as a first-time player. Returning users will see their game stats.
Guess the randomly generated number between 1 and 1000:
If your guess is too high, you'll be told, "It's lower than that."
If your guess is too low, you'll be told, "It's higher than that."
Non-integer inputs are rejected with a message: "That is not an integer, guess again."
Once you guess the correct number, the game congratulates you and updates your statistics in the database.
Project Structure
bash
Kodu kopyala
number_guessing_game/
├── number_guess.sh      # The main Bash script
└── README.md            # Project documentation
Example Gameplay
yaml
Kodu kopyala
$ ./number_guess.sh
Enter your username:
john_doe
Welcome back, john_doe! You have played 5 games, and your best game took 3 guesses.
Guess the secret number between 1 and 1000:
500
It's higher than that, guess again:
750
It's lower than that, guess again:
600
You guessed it in 3 tries. The secret number was 600. Nice job!
Database Backup and Restore
To back up your database:

bash
Kodu kopyala
pg_dump -cC --inserts -U freecodecamp number_guess > number_guess.sql
To restore your database:

bash
Kodu kopyala
psql -U postgres < number_guess.sql
Technologies Used
Bash: For scripting and game logic.
PostgreSQL: For storing user data and game statistics.
License
This project is open-source and available under the MIT License.

Acknowledgments
This project was developed as part of the freeCodeCamp Relational Databases Certification program. Special thanks to freeCodeCamp for providing the learning platform.

Replace <repository-url> with your repository's URL when you're ready to publish.
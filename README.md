# task-4-rock-paper-scissors
import random


def get_computer_choice():
    """Generate a random choice for the computer."""
    return random.choice(['rock', 'paper', 'scissors'])


def determine_winner(user_choice, computer_choice):
    """Determine the winner based on the game rules."""
    if user_choice == computer_choice:
        return "tie"
    elif (user_choice == 'rock' and computer_choice == 'scissors') or \
            (user_choice == 'scissors' and computer_choice == 'paper') or \
            (user_choice == 'paper' and computer_choice == 'rock'):
        return "win"
    else:
        return "lose"


def play_game():
    user_score = 0
    computer_score = 0

    print("Welcome to Rock, Paper, Scissors!")
    while True:
        print("\nChoose one: rock, paper, or scissors.")

        # Get the user's choice
        user_choice = input("Your choice: ").lower()

        # Validate the user's input
        if user_choice not in ['rock', 'paper', 'scissors']:
            print("Invalid choice! Please choose 'rock', 'paper', or 'scissors'.")
            continue

        # Get the computer's choice
        computer_choice = get_computer_choice()
        print(f"Computer chose: {computer_choice}")

        # Determine the winner
        result = determine_winner(user_choice, computer_choice)
        if result == "win":
            user_score += 1
            print(f"You win this round! {user_choice.capitalize()} beats {computer_choice}.")
        elif result == "lose":
            computer_score += 1
            print(f"You lose this round! {computer_choice.capitalize()} beats {user_choice}.")
        else:
            print("It's a tie!")

        # Display scores
        print(f"Score - You: {user_score}, Computer: {computer_score}")

        # Ask if the user wants to play another round
        play_again = input("\nDo you want to play another round? (yes/no): ").lower()
        if play_again != 'yes':
            print("\nThanks for playing!")
            break


if __name__ == "__main__":
    play_game()


output:
Welcome to Rock, Paper, Scissors!

Choose one: rock, paper, or scissors.
Your choice: scissors
Computer chose: paper
You win this round! Scissors beats paper.
Score - You: 1, Computer: 0

Do you want to play another round? (yes/no): no

Thanks for playing!

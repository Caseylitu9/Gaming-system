#include <stdio.h>
#include <stdlib.h>
#include <time.h>

void play_game();
int get_computer_choice();
int get_user_choice();
void determine_winner(int computer_choice, int user_choice);

int main() {
    int choice;

    while (1) {
        printf("\n\n---Gaming System---\n");
        printf("1. Play game\n");
        printf("2. Exit\n");
        printf("Enter your choice: ");

        scanf("%d", &choice);

        switch (choice) {
            case 1:
                play_game();
                break;

            case 2:
                exit(0);
                break;

            default:
                printf("Invalid choice\n");
        }
    }

    return 0;
}

void play_game() {
    int computer_choice, user_choice;

    printf("\n---Rock-Paper-Scissors Game---\n");
    printf("1. Rock\n");
    printf("2. Paper\n");
    printf("3. Scissors\n");

    user_choice = get_user_choice();
    computer_choice = get_computer_choice();

    printf("Computer choice: %d\n", computer_choice);

    determine_winner(computer_choice, user_choice);
}

int get_user_choice() {
    int choice;

    printf("Enter your choice: ");
    scanf("%d", &choice);

    return choice;
}

int get_computer_choice() {
    srand(time(NULL));
    return rand() % 3 + 1;
}

void determine_winner(int computer_choice, int user_choice) {
    if (computer_choice == user_choice) {
        printf("Tie game!\n");
    } else if (computer_choice == 1 && user_choice == 3) {
        printf("Computer wins!\n");
    } else if (computer_choice == 2 && user_choice == 1) {
        printf("Computer wins!\n");
    } else if (computer_choice == 3 && user_choice == 2) {
        printf("Computer wins!\n");
    } else {
        printf("You win!\n");
    }
}


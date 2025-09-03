# C Program to Represent a Playing Card and Generate Random Cards

```c
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

enum Suit { HEARTS, DIAMONDS, CLUBS, SPADES };

struct Card {
    enum Suit suit;
    int rank; 
};

struct Card generateRandomCard() {
    struct Card c;
    c.suit = rand() % 4;
    c.rank = rand() % 13 + 1;
    return c;
}

void printCard(struct Card c) {
    char *suits[] = {"Hearts", "Diamonds", "Clubs", "Spades"};
    char *ranks[] = {"", "Ace", "2", "3", "4", "5", "6", "7", "8", "9", "10", "Jack", "Queen", "King"};

    printf("Card: %s of %s\n", ranks[c.rank], suits[c.suit]);
}

int main() {
    srand(time(NULL)); 

    struct Card card = generateRandomCard();
    printCard(card);

    return 0;
}

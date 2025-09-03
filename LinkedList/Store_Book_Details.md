# C Program to Store Book Details Using a Structure

```c
#include <stdio.h>

struct Book {
    char title[100];
    char author[100];
    long int ISBN;
    int pages;
};

void readBookDetails(struct Book *b) {
    printf("Enter book title: ");
    getchar(); // to consume leftover newline
    fgets(b->title, sizeof(b->title), stdin);
    b->title[strcspn(b->title, "\n")] = '\0'; // remove newline

    printf("Enter author name: ");
    fgets(b->author, sizeof(b->author), stdin);
    b->author[strcspn(b->author, "\n")] = '\0'; // remove newline

    printf("Enter ISBN number: ");
    scanf("%ld", &b->ISBN);

    printf("Enter number of pages: ");
    scanf("%d", &b->pages);
}

void printBookDetails(struct Book b) {
    printf("\nBook Details:\n");
    printf("Title: %s\n", b.title);
    printf("Author: %s\n", b.author);
    printf("ISBN: %ld\n", b.ISBN);
    printf("Pages: %d\n", b.pages);
}

int main() {
    struct Book myBook;

    readBookDetails(&myBook);
    printBookDetails(myBook);

    return 0;
}
```

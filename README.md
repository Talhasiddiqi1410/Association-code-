# Association-code-
#include <iostream>
#include <vector>
using namespace std;

class Book; // Forward declaration

class Author {
public:
    string name;
    vector<Book*> books;

    Author(string name) : name(name) {}

    void addBook(Book* book);
};

class Book {
public:
    string title;
    Book(string title) : title(title) {}
};

void Author::addBook(Book* book) {
    books.push_back(book);
}

int main() {
    Author author1("George Orwell");
    Book book1("1984"), book2("Animal Farm");

    author1.addBook(&book1);
    author1.addBook(&book2);

    cout << author1.name << " has written: ";
    for (auto book : author1.books) {
        cout << book->title << ", ";
    }
    return 0;
}


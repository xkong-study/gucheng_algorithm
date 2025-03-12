# OCP & SRP Explained with Play Cards & Public Library

## 🃏 Open-Closed Principle (OCP) – Playing Cards Analogy

👉 'Software should be open for extension but closed for modification.'

Imagine a Deck of Playing Cards... Instead of modifying `Deck` every time a new suit is added, we create new `Suit` classes like `JokerSuit` or `StarSuit` without changing the existing code.

### 🚫 Bad Design (Violating OCP)
```

class Deck {  
   constructor() {  
      this.cards = [];  
      this.suits = ["Spades", "Hearts", "Clubs", "Diamonds"];  
      this.ranks = ["2", "3", ..., "King", "Ace"];  
      this.createDeck();  
}  
createDeck() {  
   for (let suit of this.suits) {  
     for (let rank of this.ranks) {  
        this.cards.push({ suit, rank });  
     }  
   }  
 }  
}  
```
### ✅ Good Design (Following OCP)
```

class Suit {  
   constructor(name) {  
      this.name = name;  
  }  
}  
class StandardSuit extends Suit {  
   constructor() {  
   super("Standard");  
 }  
}  
class Joker extends Suit {  
   constructor() {  
   super("Joker");  
 }  
}  
class Deck {  
   constructor() {  
      this.cards = [];  
      this.suits = [new StandardSuit(), new Joker()];  
      this.createDeck();  
}  
createDeck() {  
   for (let suit ofthis.suits) {  
     // Logic to add corresponding cards  
  }  
 }  
}  
```
## 🏛️ Single Responsibility Principle (SRP) – Public Library Analogy

👉 'A class should have only one responsibility.'

A library does many things: managing books, handling members, and borrowing books. Instead of one big class, we split responsibilities into different classes.

### 🚫 Bad Design (Violating SRP)
```
class Library {  
   constructor() {  
      this.books = [];  
      this.members = [];  
   }  
   addBook(book) {  
      this.books.push(book);  
   }  
   registerMember(member) {  
      this.members.push(member);  
   }  
   checkoutBook(member, book) {  
       if (this.books.includes(book)) {  
       console.log(`${member} checked out ${book}`);  
    }  
  }  
} 
```
### ✅ Good Design (Following SRP)
```
class BookManager {  
   constructor() {  
      this.books = [];  
}  
addBook(book) {  
      this.books.push(book);  
}  
findBook(title) {  
   return this.books.find(book = book.title === title);  
  }  
}  
class MemberManager {  
   constructor() {  
      this.members = [];  
}  
registerMember(member) {  
      this.members.push(member);  
}  
isMemberRegistered(name) {  
  return this.members.includes(name);  
 }  
}  
class BorrowingSystem {  
   constructor(bookManager, memberManager) {  
      this.bookManager = bookManager;  
      this.memberManager = memberManager;  
}  
checkoutBook(member, bookTitle) {  
if (this.memberManager.isMemberRegistered(member)) {  
    let book = this.bookManager.findBook(bookTitle);  
if (book) {  
     console.log(`${member} checked out "${bookTitle}"`);  
} else {  
   console.log("Book not found.");  
  }  
} else {  
   console.log("Member not registered.");  
  }  
 }  
}  
```
## 🔑 Interview Summary

1️⃣ **Open-Closed Principle (OCP) – Playing Cards**  
 'A system should be open for extension but closed for modification.'  
 Example: Instead of modifying `Deck` every time a new suit is added, we create new `Suit` classes like `JokerSuit` or `StarSuit` without changing the existing code.  

2️⃣ **Single Responsibility Principle (SRP) – Public Library**  
 'A class should have only one responsibility.'  
 Example: Instead of one giant `Library` class handling books, members, and borrowing, we split it into `BookManager`, `MemberManager`, and `BorrowingSystem`.  

🚀 With these real-world analogies, the interviewer will definitely remember your answer! 🎯





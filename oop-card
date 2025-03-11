# Refactored JavaScript Code for Card Game

This document contains the refactored JavaScript code for implementing a card game using Object-Oriented Programming (OOP).

// Card class representing a playing card  
class Card {  
constructor(suit, value) {  
this.suit = suit; // e.g., "Hearts", "Spades"  
this.value = value; // e.g., "A", "2", "K"  
}  
<br/>// Returns a string representation of the card  
toString() {  
return \`${this.value} of ${this.suit}\`;  
}  
}  
<br/>// Game class managing the deck and comparisons  
class Game {  
constructor() {  
this.suits = \["Hearts", "Spades", "Clubs", "Diamonds"\];  
this.values = \["A", "2", "3", "4", "5", "6", "7", "8", "9", "10", "J", "Q", "K"\];  
this.cards = \[\]; // Stores Card objects  
}  
<br/>// Adds a card to the game  
addCard(suit, value) {  
this.cards.push(new Card(suit, value));  
}  
<br/>// Returns the string representation of a card by index  
cardString(index) {  
return index >= 0 && index < this.cards.length ? this.cards\[index\].toString() : "";  
}  
<br/>// Determines if cardA beats cardB  
cardBeats(cardA, cardB) {  
if (cardA >= this.cards.length || cardB >= this.cards.length) return false;  
<br/>let card1 = this.cards\[cardA\];  
let card2 = this.cards\[cardB\];  
<br/>let index1 = this.values.indexOf(card1.value);  
let index2 = this.values.indexOf(card2.value);  
<br/>return index1 > index2; // Higher index means stronger card  
}  
}  
<br/>// Generator function for input handling  
function\* main() {  
const game = new Game();  
<br/>let \[suit, value\] = (yield).split(" ");  
game.addCard(suit, value);  
console.log(game.cardString(0));  
<br/>\[suit, value\] = (yield).split(" ");  
game.addCard(suit, value);  
console.log(game.cardString(1));  
<br/>console.log(game.cardBeats(0, 1));  
}  
<br/>// Exception class for handling input termination  
class EOFError extends Error {}

# Design & Implementation of Card Game with Joker Support

This document describes the design principles and implementation approach for a card game that includes a Joker class, extending the base Card class. The Joker is always considered the highest-ranked card with a value of 14.

## 📌 Design Steps

1. **Define a Base \`Card\` Class** - Represents a standard playing card with a suit and a value.

2. **Introduce a \`Joker\` Class** - Inherits from \`Card\` but has a fixed value of 14, making it the strongest card.

3. **Modify the \`Game\` Class** - Supports adding both standard cards and Joker cards while handling comparisons.

4. **Implement \`cardBeats()\` Method** - Compares two cards based on predefined ranks, treating Joker separately.

5. **Ensure Scalability** - The design allows easy extension for more special cards in the future.

## 📌 Key Implementation

**1. Base \`Card\` Class**

```
constructor(suit, value) {  
  this.suit = suit;  
  this.value = value;  
}  
toString() {  
  return \`${this.value} of ${this.suit}\`;  
}  
```

**2. \`Joker\` Class (Extending \`Card\`)**

```
class Joker extends Card {  
  constructor() {  
   super("Joker", "Joker");  
  }  
  getValueIndex() {  
   return 14;
  }  
  toString() {  
   return "Joker";  
  }  
}
```

**3. \`Game\` Class with Joker Support**
```
class Game {  
  constructor() {  
    this.values = \["A", "2", "3", "4", "5", "6", "7", "8", "9", "10", "J", "Q", "K"\];  
    this.cards = \[\];  
  }  
  addCard(suit, value) {  
    if (suit === "Joker") {  
    this.cards.push(new Joker());  
    } else {  
    this.cards.push(new Card(suit, value));  
    }  
  }  
  cardBeats(cardA, cardB) {  
    if (cardA >= this.cards.length || cardB >= this.cards.length) return false;  
      let card1 = this.cards\[cardA\];  
      let card2 = this.cards\[cardB\];  
      let index1 = card1 instanceof Joker ? 14 : this.values.indexOf(card1.value);  
      let index2 = card2 instanceof Joker ? 14 : this.values.indexOf(card2.value);  
     return index1 > index2;  
   }  
}
```
## 📌 Conclusion

This design follows an object-oriented approach, ensuring modularity and scalability. The use of inheritance allows us to add new special cards easily while keeping the game logic clean and maintainable.

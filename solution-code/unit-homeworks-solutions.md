## UNIT HOMEWORKS: MEMORY GAMME SOLUTIONS

### Unit 3

1) Create four variables that simulate the cards in your game

- they should be `String` types
- two should have a value of `"queen"` and the other two should be `"king"`
- they will be representation of your cards (i.e. "queen" card)
- name your variables `cardOne`, `cardTwo`, etc.

```js
var cardOne = "queen";

var cardTwo = "queen";

var cardThree = "king";

var cardFour = "king";
```

2) Compare two queen variables

```js
cardOne == cardTwo // true
```

3) Compare a king variable with a queen variable

```js
cardOne == cardFour // false
```
---

### Unit 4

1) Create an `if else` statement checking for equality between two of your cards (you choose which ones)

```js
// `if` statement should consist of a boolean checking for equality between your created variables
if (cardTwo === cardsThree) {

} else {

}
```

2) If values are equal, execute an `alert` with the message, "You found a match!". If values are not equal, execute an `alert` with the message, "Sorry, try again.".

```js
// if the conditional is met, run the expression: alert("You found a match!")
if (cardTwo === cardsThree) {

  alert('You found a match!');

// else, run the expression: alert("Sorry, try again.")
} else {

  alert("Sorry, try again.");

}
```
---

### Unit 5

1) Find the board and set it to a variable

```js
var board = document.getElementsByClassName('board')[0];
```

2) Create a `for loop` that will iterate four times

```js
for (var i=0; i<5; i++) {

}
```

3) Create the required HTML for each card on each iteration and append to the board

```js
for (var i=0; i<5; i++) {

  // create a div element which will be used as a card
  var cardElement = document.createElement('div');

  // add a class to the card element which will help link styling
  cardElement.className = 'card';

  // append the card to the board
  board.appendChild(cardElement);

}
```

4) Create `createBoard` function

```js
function createBoard() {

}
```

5) Add your board creation logic to the function

```js
function createBoard() {

  var board = document.getElementsByClassName('board')[0];

  for (var i=0; i<5; i++) {

    // create a div element which will be used as a card
    var cardElement = document.createElement('div');

    // add a class to the card element which will help link styling
    cardElement.className = 'card';

    // append the card to the board
    board.appendChild(cardElement);

  }

}
```

6) Execute `createBoard`

```js
createBoard()
```
---
### Unit 6

1) Declare a variable, `cards`, whose value is an `Array` that consists of four `String` elements: `queen`, `queen`, `king`, `king`.

```js
// represents the cards of the game
var cards = ['queen', 'queen', 'king', 'king'];
 ```

2) Declare a variable, `cardsInPlay`, whose value is an empty array.

```js
// this array keeps track of the cards in play
var cardsInPlay = [];
```

3) Each element should have innerHTML which equals the card value (i.e. "queen")

```js
// instead of looping through a fixed number
// loop through the length of the cards
for (var i=0; i<cards.length; i++) {

  ...

  // this will set the card's innerHTML to be the element of the array
  // i.e. "king"
  cardElement.innerHTML = cards[i];

  ...

}
```

4) Add a click event listener to each card element that runs a function, `isTwoCards`

```js
for (var i=0; i<cards.length; i++) {

  ...

  // when a card is clicked the function isTwoCards will be executed
    cardElement.addEventListener('click', isTwoCards)

  ...

}

```

5) Create a function called `isMatch` to test if two cards in play are a match

```js
// this function takes an array argument
function isMatch(cards) {

  // we can then configure our previous game logic code to access the cards
  if (cards[0] === cards[1]) {

    alert("You found a match!");

  } else {

    alert("Sorry, try again.");

  }
}
```

6) Create a function called `isTwoCards` to check if two cards are in play

```js
//checks to see if there are cards in play
function isTwoCards() {

  // add card to array of cards in play
  // 'this' is not covered in the pre-work but
  // for now, just know it gives you access to the card the user clicked on
  cardsInPlay.push(this.innerHTML)

  // if you have two cards in play check for a match
  if (cardsInPlay.length === 2) {

    // pass the cardsInPlay as an argument to isMatch function
    isMatch(cardsInPlay);

    // clear cards in play array for next try
    cardsInPlay = [];

  }

}
```

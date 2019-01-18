# Elevens 7

Follow the instructions provided for Activity 7 in the student lab guide. This is more of an exploratory lab, so you will not need to copy any of your previous code into the repo. Answer the questions from the Student Guide in this document and ensure that you save and push the repo. You have one week to complete this lab.

1. What items would be necessary if you were playing a game of Elevens at your desk (not on the computer)? List the private instance variables needed for the `ElevensBoard` class.

    *
    A full deck of cards.
    The private instance variables are cards(with point values), deck, discard pile

2. Write an algorithm that describes the actions necessary to play the Elevens game.

    *
    Step 1: deal 9 card
    Step 2: If 2 selected cards equal 11 discard those 2 cards and replace them with 2 new cards
    Step 3: If there is a king queen and jack, selecting all three will discard them and replace them with 3 new cards
    Step 4: Continue game until there are no cards left
    Step 5: Else if there no moves, you lose


3. Now examine the partially implemented `ElevensBoard.java` file found in this repository. Does the `ElevensBoard` class contain all the state and behavior necessary to play the game?

    * Yes, I think that it contains every tate and behavior needed to play

4. `ElevensBoard.java` contains three helper methods. These helper methods are private because they are only called from the ElevensBoard class.

  * a. Where is the `dealMyCards` method called in ElevensBoard?

      * It's called under newGame

  * b. Which `public` methods should call the `containsPairSum11` and `containsJQK` methods?

      * isLegal should call the containsPairSum11 and containsJQK methods to check if the move is valid

  * c. It’s important to understand how the `cardIndexes` method works, and how the list that it returns is used. Suppose that `cards` contains the elements shown below. Trace the execution of the `cardIndexes` method to determine what list will be returned. Complete the diagram below by filling in the elements of the returned list, and by showing how those values index `cards`. Note that the returned list may have less than 9 elements.

    * `cards`
    |♥6|♣null|2♠|null|null|A♠|4♥|null|

| 0  | 1  |  2   | 3  |  4   |  5   | 6  | 7  |  8   |
|:--:|:--:|:----:|:--:|:----:|:----:|:--:|:--:|:----:|
| J♥ | 6♣ |`null`| 2♠ |`null`|`null`| A♠ | 4♥ |`null`|

   *  | 0 | 1 | 3 | 6 | 7 |
      |---|---|---|---|---|

| 0  | 1  | 2  | 3  | 4  | 5  | 6  | 7  | 8  |
|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|
|♥6  |♣null|2♠ |null|null|A♠  |4♥  |null|


  * d. Complete the following `printCards` method to print all of the elements of cards that are indexed by `cIndexes`.
```java
public static printCards(ElevensBoard board) {
    List<Integer> cIndexes = board.cardIndexes();
    /* Your code goes here. */
    for (List card : cIndexes){
      System.out.print(cardAt(card).toString());
    }
}
```

  * e. Which one of the methods that you identified in question 4b above needs to call the `cardIndexes` method before calling the `containsPairSum11` and `containsJQK` methods? Why?

      * isLegal needs the cards as its parameters in order to validate the move

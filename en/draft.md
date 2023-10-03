# Reduce Information to the Minimum

In the End we had the following base: 
```
Players: [p1, p2, ... p10]
big blind: amount | playerID
small blind: amount | playerID
bankroll: amount | playerID
Pot: amount
Card: Suit | Name | Value
Deck: [list of 52 cards]
Table: players | game | removePlayer | addPlayer | startGame
Game: deck | shared cards | pot | stages | bigBlindSize | smallBlindSize | compareScores | waitForMorePlayers
Player: hand | bankroll | blind | actions [ check, bet, call, raise, fold ]
Hand: Card1 | Card2
Shared Cards: [c1, c2, c3, c4, c5]
stages: [ take big blind, take small blind, deal, bet1, flop, bet2, turn, bet3, river, bet4, showdown ]
```

## Thinking about Data
Now that we think we have a good idea of the moving parts for a poker game and what they own or can do, lets reframe that into how we would represent these as data. 

```JSON
{
    "players": ["p1", "...", "p10"],
    "player": {
        "name": "bert", 
        "bankroll": 1000, 
        "Hand": ["card1", "card2"]
        },
    "card": {
        "suit": "H", 
        "name": "A", 
        "value": 11
    } 
    //etc
}
```


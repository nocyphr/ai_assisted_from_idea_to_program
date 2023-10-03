# Input
Players: [p1, p2, ... p10]
big blind: amount | playerID
small blind: amount | playerID
bankroll: amount | playerID
Pot: amount
Card: Suit | Name | Value
Deck: [list of 52 cards]
Table: players | game | removePlayer | addPlayer | startGame
Game: deck | shared cards | pot | stages | bigBlindSize | smallBlindSize | compareScores
Player: hand | bankroll | blind | actions [ check, bet, call, raise, fold ]
Hand: Card1 | Card2
Shared Cards: [c1, c2, c3, c4, c5]
stages: [ take big blind, take small blind, deal, bet1, flop, bet2, turn, bet3, river, bet4, showdown ]

Create a feature file for this. create a class structure

# Output
```python 
from enum import Enum
from typing import List, Union

class Suit(Enum):
    HEARTS = 'Hearts'
    DIAMONDS = 'Diamonds'
    CLUBS = 'Clubs'
    SPADES = 'Spades'

class Card:
    def __init__(self, suit: Suit, name: str, value: int):
        self.suit = suit
        self.name = name
        self.value = value

class Player:
    def __init__(self, playerID: str, bankroll: int):
        self.playerID = playerID
        self.bankroll = bankroll
        self.hand = []
        self.blind = None
        
    def actions(self, action: str, amount: int = 0):
        # Implement actions like check, bet, call, raise, fold
        pass

class Table:
    def __init__(self):
        self.players = []
        self.game = None

    def addPlayer(self, player: Player):
        self.players.append(player)

    def removePlayer(self, playerID: str):
        self.players = [p for p in self.players if p.playerID != playerID]

    def startGame(self):
        self.game = Game(self.players)

class Game:
    def __init__(self, players: List[Player]):
        self.deck = self._createDeck()
        self.sharedCards = []
        self.pot = 0
        self.stages = ['take big blind', 'take small blind', 'deal', 'bet1', 'flop', 'bet2', 'turn', 'bet3', 'river', 'bet4', 'showdown']
        self.bigBlindSize = 0  # Set appropriate blind size
        self.smallBlindSize = 0  # Set appropriate blind size

    def _createDeck(self) -> List[Card]:
        # Implement a function to create a deck of 52 cards
        pass

    def compareScores(self, player1: Player, player2: Player) -> Union[Player, None]:
        # Implement a function to compare the scores of two players
        pass

```
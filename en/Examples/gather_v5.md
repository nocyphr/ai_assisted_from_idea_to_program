# Input
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

Analyze my structure and optionally move ownership of certain aspects to optimize overall structure and control flow. Then Create a feature file for this. create a class structure

# Output
```python
class Card:
    def __init__(self, suit, name, value):
        self.suit = suit
        self.name = name
        self.value = value

class Deck:
    def __init__(self):
        self.cards = [Card(suit, name, value) for suit, name, value in all_possible_cards]
    
    def shuffle(self):
        pass  # Implementation of shuffling the cards
    
    def deal(self):
        pass  # Implementation of dealing the cards

class Player:
    def __init__(self, playerID, bankroll):
        self.playerID = playerID
        self.hand = None
        self.bankroll = bankroll
        self.currentBet = 0
        self.status = 'active'
    
    def bet(self, amount):
        pass
    
    def fold(self):
        pass
    
    def call(self):
        pass
    
    def raise_bet(self, amount):
        pass

class Table:
    def __init__(self):
        self.players = []
        self.game = None
        self.maxPlayers = 10
        self.currentDealer = None
    
    def addPlayer(self, player):
        pass
    
    def removePlayer(self, playerID):
        pass
    
    def startGame(self):
        pass
    
    def endGame(self):
        pass

class Game:
    def __init__(self, players, bigBlindSize, smallBlindSize):
        self.deck = Deck()
        self.sharedCards = []
        self.pot = 0
        self.stages = ['deal', 'bet1', 'flop', 'bet2', 'turn', 'bet3', 'river', 'bet4', 'showdown']
        self.bigBlindSize = bigBlindSize
        self.smallBlindSize = smallBlindSize
        self.currentPlayer = None
        self.currentStage = self.stages[0]
    
    def play(self):
        pass
    
    def waitForMorePlayers(self):
        pass
    
    def compareScores(self):
        pass
    
    def nextStage(self):
        pass
    
    def distributePot(self):
        pass

```
# Input
Number of players: 2-10
big blind: amount | playerID
small blind: amount | playerID
bankroll: amount | playerID
Pot: amount
Card: Suit | Name | Value

Game-stages: 
- Blinds
- Cards dealt
- Bet #1 
- Flop (first three cards reveal)
- Bet #2
- Turn (card #4 reveal)
- Bet #3
- River (card #5 reveal)
- Bet #4
- Showdown [IF 2+ players remain, otherwise default win for last player remaining]

Actions a player can take: 
- check [ if no other player has bet in that betting round ] - not making a bet, next player please
- bet [if no other player has bet in that round] - set a bet
- call [if there has been a bet in the current round ] - player matches the current highest bet to stay in the hand
- raise [ if there has been a bet in the current round ] - increases the bet, and all the following players must either call the raised bet, raise again, or fold
- fold - player discards their hand, wait for new game

Score-ranking: 
- **Royal Flush**: A, K, Q, J, 10, all of the same suit
- **Straight Flush**: Five consecutive cards of the same suit
- **Four of a Kind**: Four cards of the same rank
- **Full House**: Three cards of one rank and two cards of another rank
- **Flush**: Five cards of the same suit, not in sequence
- **Straight**: Five consecutive cards of different suits
- **Three of a Kind**: Three cards of the same rank
- **Two Pair**: Two cards of one rank and two cards of another rank
- **One Pair**: Two cards of the same rank
- **High Card**: The highest card in the hand if no other hand is made

Create a feature file for this. create a class structure


# Output
```python
from enum import Enum
from typing import List, Tuple

class Suit(Enum):
    HEARTS = "Hearts"
    DIAMONDS = "Diamonds"
    CLUBS = "Clubs"
    SPADES = "Spades"

class Card:
    def __init__(self, suit: Suit, name: str, value: int):
        self.suit = suit
        self.name = name
        self.value = value

class Player:
    def __init__(self, player_id: int, bankroll: int):
        self.player_id = player_id
        self.bankroll = bankroll
        self.hand = []

    def bet(self, amount: int):
        pass

    def fold(self):
        pass

    def call(self, amount: int):
        pass

    def raise_bet(self, amount: int):
        pass

    def check(self):
        pass

class PokerGame:
    def __init__(self, num_players: int):
        self.num_players = num_players
        self.players = [Player(i, 1000) for i in range(num_players)]
        self.pot = 0
        self.community_cards = []
        self.current_bet = 0

    def start_game(self):
        pass

    def deal_cards(self):
        pass

    def betting_round(self):
        pass

    def reveal_flop(self):
        pass

    def reveal_turn(self):
        pass

    def reveal_river(self):
        pass

    def showdown(self):
        pass

    def rank_hands(self):
        pass

    def award_pot(self, winner: Player):
        pass
```
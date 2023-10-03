# Input
Players: [p1, p2, ... p10]
big blind: amount | playerID
small blind: amount | playerID
bankroll: amount | playerID
Pot: amount
Card: Suit | Name | Value
Deck: [list of 52 cards]
Table: players | game
Game: deck | shared cards | pot | turn
Player: hand | bankroll | blind
Hand: Card1 | Card2
Shared Cards: [c1, c2, c3, c4, c5]

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
from typing import List, Tuple
from enum import Enum


class Suit(Enum):
    HEARTS = "Hearts"
    DIAMONDS = "Diamonds"
    CLUBS = "Clubs"
    SPADES = "Spades"


class Rank(Enum):
    # Add all ranks from 2 to 10, J, Q, K, A


class Card:
    def __init__(self, suit: Suit, rank: Rank):
        self.suit = suit
        self.rank = rank

    def __repr__(self):
        return f"{self.rank.name} of {self.suit.name}"


class Deck:
    def __init__(self):
        self.cards = [Card(suit, rank) for suit in Suit for rank in Rank]

    def shuffle(self):
        # Implement shuffle method

    def draw(self) -> Card:
        # Implement draw card method


class Hand:
    def __init__(self, cards: List[Card]):
        self.cards = cards

    def add_card(self, card: Card):
        self.cards.append(card)

    # Other methods to evaluate the hand


class Player:
    def __init__(self, player_id: str, bankroll: int):
        self.player_id = player_id
        self.bankroll = bankroll
        self.hand = None
        self.blind = None

    def bet(self, amount: int):
        # Implement bet method

    def call(self, amount: int):
        # Implement call method

    def raise_bet(self, amount: int):
        # Implement raise method

    def fold(self):
        # Implement fold method


class Table:
    def __init__(self, players: List[Player], game):
        self.players = players
        self.game = game


class Game:
    def __init__(self, deck: Deck, pot: int = 0):
        self.deck = deck
        self.shared_cards = []
        self.pot = pot
        self.turn = None

    def deal_cards(self):
        # Implement deal cards method

    def reveal_card(self):
        # Implement reveal card method

    def determine_winner(self):
        # Implement determine winner method based on hand rankings

```
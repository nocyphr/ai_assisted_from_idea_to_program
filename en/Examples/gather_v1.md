# Input
Number of players: 2-10
big blind:
small blind: 
bankroll [per player]
Pot
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


create a feature file based on this. Create a class structure

# Output
```python
class Card:
    def __init__(self, suit, name, value):
        self.suit = suit
        self.name = name
        self.value = value


class Player:
    def __init__(self, bankroll):
        self.bankroll = bankroll
        self.hand = []
        self.current_bet = 0

    def check(self):
        pass

    def bet(self, amount):
        pass

    def call(self, amount):
        pass

    def raise_bet(self, amount):
        pass

    def fold(self):
        pass


class PokerGame:
    def __init__(self, players, big_blind, small_blind):
        self.players = players  # List of Player objects
        self.big_blind = big_blind
        self.small_blind = small_blind
        self.community_cards = []
        self.pot = 0

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
```
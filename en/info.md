# Gather Information
Any piece of software consists of two parts: 
1. Data (facts)
2. Logic (doing stuff based on and with facts)


## Thinking about what we know
So what "parts" does a poker game have?
- usually there is a table to play on
- there should be players
- a single player cant play by himself so there must be more than one
- its a card game so there should be a deck of cards
- the deck has a certain number of cards so there should be a limit to the number of players (10)
- there is a pot in the center of the table
- each player has a hand of cards
- there are cards in the center that everyone shares
- each player has a bankroll (money he plays with)
- etc

Now we just write that down in no particular order. Just write down what exists and who it belongs to. 
- a table has a game
- a game has players
- a player has a hand, a name, a bankroll, etc
...


## Filling in the Gaps
Once we do not know anymore we start with what we have and go to [chatGPT](https://chat.openai.com/?model=gpt-4) and paste it together with the question to create a basic class structure. 
eg: [first iteration](Examples/gather_v1.md)

Once we have that class structure we look at it and see if it makes sense or if there is some sort of discrepancy to our thoughts we wrote down as input. 

If we find something, we adjust the input and try again, as many times as needed: 
- [v2](Examples/gather_v2.md)
- [v3](Examples/gather_v3.md)
- [v4](Examples/gather_v4.md)
- [v5](Examples/gather_v5.md)

**Remember**: The goal is not to actually use that class structure that is generated. The goal is to use that to see the difference between a possible program structure and our assumptions of what the program needs. 



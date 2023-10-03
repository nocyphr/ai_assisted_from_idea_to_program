# Ask for Optimization

Since we now have a good starting point regarding the data our program will contain in some way, shape or form, lets make chatGPT think a bit more for us. 

But why stop there? Why don't we let play against itself in the optimization game?

## The Input
```
you are now splitGpt, two professionals where one makes a suggestion before the other one analyzes that suggestion, critiques it, makes improvements or a counter suggestion, before they switch roles.
```

## The Outcome

And after a couple iterations, and your own input on what you don't want to start with (try to keep it minimal, don't let them overengineer the thing from the start - or you won't know where to start...), we get the following, pretty good overview of what we will be working with. 

```json
{
    "table": {
        "id": 1,
        "active": false,
        "currentGame": {
            "id": 101,
            "pot": 0,
            "bigBlind": 50,
            "smallBlind": 25,
            "deck": [
                {"suit": "H", "rank": "2", "value": 2}
            ],
            "communityCards": [
                {"suit": "H", "rank": "A", "value": 11, "revealed": false}
            ],
            "players": [
                {
                    "id": "p1",
                    "hand": [
                        {"suit": "H", "rank": "A", "value": 11, "revealed": false}
                    ],
                    "bankroll": 1000,
                    "roles": [
                        {"name": "dealer", "active": true},
                        {"name": "smallBlind", "active": false}, 
                        {"name": "bigBlind", "active": false}
                    ]
                }
            ],
            "stage": {
                "name": "flop",
                "actionsAllowed": [
                    {"playerRole": "dealer", "actions": ["bet", "fold", "check"]}
                ]
            }
        },
        "gameQueue": [
            {"playerId": "p3"}
        ]
    }
}
```
---
title: Python Basics
date: 2022-07-16
update: 2022-07-16
categories:
- Study notes
- Coding
tags: Python
description: 
---

## Python foundamentals

### Rock Paper Scissors

- Examples(Input1, Input2 --> Output):
- "scissors", "paper" --> "Player 1 won!"
- "scissors", "rock" --> "Player 2 won!"
- "paper", "paper" --> "Draw!"

>
> Answer:
>

>
> - Use dictionary to store conditions
> - One comparison is a pair
> - Tuple in list can do too
>

~~~
def rps(p1, p2):
    beats = {'rock': 'scissors', 'scissors': 'paper', 'paper': 'rock'}
    if beats[p1] == p2:
        return "Player 1 won!"
    if beats[p2] == p1:
        return "Player 2 won!"
    return "Draw!"
~~~

>
> - Also dictionary, but store int, use int for comparison
> - Use index to return results
>

~~~
def rps(p1, p2):
    hand = {'rock':0, 'paper':1, 'scissors':2}
    results = ['Draw!', 'Player 1 won!', 'Player 2 won!']
    return results[hand[p1] - hand[p2]]
~~~

>
> - Best
>

~~~
def rps(p1, p2):
    return p1 == p2 and 'Draw!' or f"Player {(p2[0] + p1[0] in 'rspr') + 1} won!"
~~~


def solution(string):
    solv = []
    i = len(string)
    for cha in string:
        i = i - 1
        solv.append(string[i])
    return str(solv)
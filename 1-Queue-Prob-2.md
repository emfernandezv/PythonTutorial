# Problem Solve
## Excercise 2: Hot Potato Game
Implement a "Hot Potato" game using a queue. In this game, a potato is passed from one person to another in a circle. When the game starts, a queue is formed with the names of the players. The potato is passed from player to player in the queue, and after a certain number of passes, the player holding the potato is eliminated. The game continues until only one player is left. Write the code to implement the Hot Potato game using the queue definition provided.

````python
from collections import deque

def hot_potato(players, passes):
    # Your code starts here

    # Last player remaining is the winner
    print(f"Player {winner} wins!")

# Example usage
players = ["Alice", "Bob", "Charlie", "Dave", "Eve"]
passes = 3

hot_potato(players, passes)
````
The output should be:
````python
Player Dave eliminated
Player Charlie eliminated
Player Eve eliminated
Player Bob eliminated
Player Alice wins!
````
Compare your code:
<details markdown="1">
<summary>Solution</summary>
<br>

````python
from collections import deque

def hot_potato(players, passes):
    queue = deque(players)

    while len(queue) > 1:
        for _ in range(passes):
            # Rotate the queue to simulate passing the potato
            queue.rotate(-1)

        # Player with the potato is eliminated
        eliminated_player = queue.popleft()
        print(f"Player {eliminated_player} eliminated")

    # Last player remaining is the winner
    winner = queue[0]
    print(f"Player {winner} wins!")

# Example usage
players = ["Alice", "Bob", "Charlie", "Dave", "Eve"]
passes = 3

hot_potato(players, passes)
````
</details>

[GO BACK - QUEUE Main](1-Queue.md)
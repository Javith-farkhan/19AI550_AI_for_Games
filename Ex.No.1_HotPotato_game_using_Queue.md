## Ex.No: 1 Implementation of HotPotato game using Queue

## DATE: 09-08-2024
## REGISTER NUMBER: 212221240017
## AIM:

To write a python program to simulate the process of passing an item among players and eliminating players based on the given rules until a single winner is determined.

## Algorithm:

Initialize the Queue: Create a queue and enqueue all the participants.

Pass the Potato: Dequeue the first person in the queue and enqueue them at the end. This simulates passing the potato.

Count the Passes: Repeat the passing for a given number of times.

Eliminate the Holder: After the set number of passes, remove the person who holds the potato (dequeue the front of the queue).

Repeat: Continue the process until only one person remains in the queue.

## Program:
```
import queue
import random
import time

def hot_potato(names, num):
    sim_queue = queue.Queue()

    for name in names:
        sim_queue.put(name)

    while sim_queue.qsize() > 1:
        for _ in range(num):
            sim_queue.put(sim_queue.get())
        eliminated = sim_queue.get()
        print(f"{eliminated} is eliminated!")

    return sim_queue.get()

def main():
    players = ["Alice", "Bob", "Charlie", "David", "Eve"]
    #num_passes = random.randint(1, 10)
    num_passes=1
    print("Hot Potato Game Start!")
    time.sleep(1)
    winner = hot_potato(players, num_passes)
    print(f"\nThe winner is: {winner}")

if __name__ == "_main_":
    main()
```

## Output:

![356533796-2e4cd695-97d3-4ca7-adaf-4b1be04cf6ca](https://github.com/user-attachments/assets/99c98632-c10f-4efe-ab23-c020a6db4f03)

## Result:

Thus the simple HotPotato game was implemented using Queue.





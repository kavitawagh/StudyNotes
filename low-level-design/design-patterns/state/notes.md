Lets an object alter its behavior when its internal state changes.
This design pattern is closely related to Finite State Machine, states and transitions.

State design pattern is similar to Stategy with one difference. Stategies are not aware of each other but States are aware if each other. State can change the state of object from current state to another.
For example:
```
Player
- state
+ Player()
+ changeState(State s)
+ clickLock()
+ clickPlay()
+ clickReady
+ startPlayback()

IState
- player
+ clickLock()
+ clickPlay()
+ clickReady()

LockedState
PlayState
ReadyState

ReadyState:

 def clickPlay():
        player.startPlayback()
        player.changeState(new PlayingState(player))
```

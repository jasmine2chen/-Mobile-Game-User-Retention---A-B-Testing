#  A/B Testing Mobile Gaming User Retention 

## Background
Cookie Cats is a hugely popular mobile puzzle game developed by Tactile. It's a classic "connect three"-style puzzle game where the player must connect tiles of the same color to clear the board and win the level. It also features singing cats.

As players progress through the levels of the game, they will occasionally encounter gates that force them to wait a non-trivial amount of time or make an in-app purchase to progress. In addition to driving in-app purchases, these gates serve the important purpose of giving players an enforced break from playing the game, hopefully resulting in that the player's enjoyment of the game being increased and prolonged.

I will analyze an AB-test where we move the first gate in Cookie Cats from gate/level 30 to gate/level 40. In particular, I will look at the impact on player retention.

## Dataset
The data contains information of 90,189 players that installed the game while the AB-test was running. The variables are:

- userid: a unique number that identifies each player.
- version: whether the player was put in the control group (gate_30 - a gate at level 30) or the group with the moved gate (gate_40 - a gate at level 40).
- sum_gamerounds: the number of game rounds played by the player during the first 14 days after install.
- retention_1: did the player come back and play 1 day after installing?
- retention_7: did the player come back and play 7 days after installing?

## Analysis
Two A/B testing methods are performed to analyze the impact of placing first gate at level 30 vs level 40 on the retention rate
- bootstrap simulation
- Python package statsmodels.api

## Conclusions
Both bootstrap and statsmodels.api results show that there is strong evidence that 7-day retention is higher when the gate is at level 30 than when it is at level 40 (99% confident according to statsmodels.api result). Similarly, 1-day retention is higher when the gate is at level 30 than when it is at level 40 (95% confident according to statsmodels.api result). If we want to keep retention high, for both 1-day and 7-day retention, we should not move the gate from level 30 to level 40. 
These inferences are strictly based on data available. This analysis acknowledges its limitations due to factors not included in the data.


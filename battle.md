# Battle System

The battle system is a core component of the game, allowing players to test their strength and earn rewards.

## Initiating a Battle
A player can challenge another using `/battle [@user]`. The challenged player must accept for the battle to begin.

## Combat Resolution
The winner is determined by a weighted formula that combines player attributes, item bonuses, and a small random factor.

-   **Formula:** `Combat Score = (STR * 1.2) + (DEX * 1.1) + (AGI * 1.1) + (INT * 1.0) + (DEF * 0.9) + (VIT * 1.0) + (LUK * 0.5)`
-   This score is then modified by:
    -   Active poison effects.
    -   Equipped artifact bonuses.
    -   A random variance of +/- 5% to prevent ties and ensure unpredictability.

The player with the higher final score wins the battle.

## Rewards and Penalties
-   **Winner:** Receives a base amount of coins and XP, with bonuses based on the level difference between the players.
-   **Loser:** Loses a small amount of coins (a "repair fee"). No XP is lost.

## Battle Logs
Every battle is recorded and can be viewed with `/battlehistory`. The log includes the participants, the winner, and a snapshot of the key stats at the time of the battle.
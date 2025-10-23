# Battle System

The battle system is the heart of player-versus-player interaction. It resolves combat based on a combination of a player's base stats, their equipped items, active poisons, and their chosen character.

## Initiating a Battle
A player can challenge another using `/battle [@user]`. The challenged player must accept for the battle to begin.

## Core Battle Attributes

Each attribute plays a specific role in combat:

-   **Strength (STR):** Directly increases the damage dealt by physical attacks. The primary stat for brute-force characters.
-   **Dexterity (DEX):** Improves accuracy, reducing the chance your attacks will miss. It also increases the damage of precision-based skills and critical hit chance.
-   **Agility (AGI):** Determines attack speed and evasion. A high AGI allows you to attack more frequently (in a turn-based model) or increases your chance to dodge an enemy's attack.
-   **Intelligence (INT):** Powers special and elemental abilities. It also enhances the effectiveness of certain poisons and artifacts and can provide resistance to mental attacks.
-   **Defense (DEF):** Reduces the amount of physical damage taken from enemy attacks.
-   **Vitality (VIT):** Increases your total health pool (HP) and resilience. A high VIT allows you to survive more hits.
-   **Luck (LUK):** A wildcard stat that influences many random factors, including critical hit chance, dodge rate, and the likelihood of beneficial effects from items.



## Combat Resolution Formula

The winner is determined by calculating a **Total Combat Score** for each player. The formula now explicitly includes all possible bonuses.

### Step 1: Calculate Total Stats
First, we sum the player's base stats with all active modifiers:
`Total STR = Base STR + Character STR + Artifact STR + Poison STR`
`Total DEX = Base DEX + Character DEX + Artifact DEX + Poison DEX`
*(...and so on for AGI, INT, DEF, VIT, and LUK)*

-   **Formula:** `Combat Score = (STR * 1.2) + (DEX * 1.1) + (AGI * 1.1) + (INT * 1.0) + (DEF * 0.9) + (VIT * 1.0) + (LUK * 0.5)`
-   This score is then modified by:
    -   Active poison effects.
    -   Equipped artifact bonuses.
    -   A random variance of +/- 5% to prevent ties and ensure unpredictability.

The player with the higher final score wins the battle.

### Step 2: Calculate Combat Score
The Total Stats are then plugged into the weighted formula:

## Rewards and Penalties
-   **Winner:** Receives a base amount of coins and XP, with bonuses based on the level difference between the players.
-   **Loser:** Loses a small amount of coins (a "repair fee"). No XP is lost.

## Battle Logs
Every battle is recorded and can be viewed with `/battlehistory`. The log includes the participants, the winner, and a snapshot of the key stats at the time of the battle.
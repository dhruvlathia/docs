# Stealing System

Stealing is a high-risk, high-reward mechanic for players willing to engage in criminal activity.

## How it Works
-   Use `/steal [@user]` to attempt to steal from another player's **wallet** (banked coins are safe).
-   There is a cooldown period after each attempt, successful or not.

## Success Chance
The success chance is calculated based on multiple factors:

-   **Base Chance:** 40%
-   **Level Difference:** `(Thief Level - Target Level) * 1%`. A higher level gives you an advantage.
-   **LUK Stat:** `(Thief LUK - Target LUK) * 0.25%`. Luck plays a role.
-   **Offensive Items:** Poisons and Artifacts equipped by the thief can increase the success chance.
-   **Defensive Items:** Artifacts equipped by the target are the primary defense and can drastically reduce the success chance.

The final chance is clamped between a minimum of 5% and a maximum of 95%.

## Outcomes
-   **Success:** The thief steals a random percentage (5-20%) of the target's wallet coins. The thief also gains XP.
-   **Failure:** The thief pays a penalty fee (a percentage of their own wallet) and gains no XP. Some defensive artifacts may inflict additional penalties on the thief, such as stunning them (increasing their steal cooldown) or reflecting a "fine" back at them.
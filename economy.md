# XP, Leveling, and Economy

This document details the game's economic loop, including how players earn XP, level up, and manage their currency.

## Experience Points (XP) & Leveling

Players start at Level 1. The primary goal of gaining XP is to level up, which strengthens a player's profile and unlocks game features.

### How to Gain XP
-   **Winning Battles:** The primary source of XP.
    -   Defeating a higher-level player grants a significant XP bonus.
    -   Defeating a lower-level player grants minimal XP.
-   **Claiming Characters:**
    -   Common: 5 XP
    -   Rare: 15 XP
    -   Epic: 40 XP
    -   Legendary: 100 XP
    -   Mythical: 250 XP
-   **Successful Bets:** Winning a bet grants a small, fixed amount of XP.
-   **Successful Steals:** A successful steal provides a moderate amount of XP.
-   **Using Specific Artifacts:** Some artifacts provide a passive XP boost.

### XP Requirements
The XP required to level up follows an exponential curve to ensure progression slows at higher levels.
-   **Formula:** `XP_for_next_level = 100 * (current_level ^ 1.5)`
    -   Level 1 to 2: 100 XP
    -   Level 10 to 11: ~3,162 XP
    -   Level 50 to 51: ~35,355 XP

### Benefits of Leveling Up
-   **Attribute Points:** Gain +5 attribute points to distribute among STR, INT, DEX, AGI, DEF, VIT, and LUK.
-   **Coin Reward:** Receive **`1000 * new_level` coins**.
-   **Artifact Slots:** Increase the maximum number of equippable artifacts (`floor(level / 2)`).
-   **Bank Capacity:** Increase bank storage (`level^2 * 500`).
-   **Unlocks:** Higher levels may be required to purchase or upgrade powerful artifacts.

## Currency: The `coin`

The `coin` is the lifeblood of the economy.

### Earning Coins
-   Level-up rewards.
-   Winning battles.
-   Winning bets.
-   Selling characters or items to other players.
-   Successful steals.
-   Passive income from certain artifacts.

### Spending Coins
-   Purchasing poisons and artifacts from the shop.
-   Upgrading artifacts.
-   Placing bets.
-   Paying trade fees in a marketplace.
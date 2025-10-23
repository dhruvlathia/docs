# Core Features

This document outlines the primary features of the Anime Character Catcher Bot.

### Character Collection
-   **Automatic Drops:** Anime characters appear randomly in chats.
-   **Claiming:** The first user to use the `/grab <character_name>` command claims the character.
-   **Rarity System:** Characters have rarities (Common, Rare, Epic, Legendary, Mythical) which affect their stats and value.
-   **Inventory:** All collected characters are stored in a user's personal inventory.

### Player Progression
-   **Leveling System:** Players earn XP to level up, unlocking new abilities and rewards.
-   **Core Attributes:** Each player has stats: Strength (STR), Intelligence (INT), Dexterity (DEX), Agility (AGI), Defense (DEF), Vitality (VIT), and Luck (LUK).
-   **Level-Up Rewards:** Upon leveling up, a player receives **`1000 * new_level` coins**. (e.g., reaching Level 10 grants 10,000 coins).

### Economy
-   **Currency:** The in-game currency is the **`coin`**.
-   **Shop:** A central place to buy Poisons, Artifacts, and other items.
-   **Bank:** A secure place to store coins. Bank capacity is determined by the formula: `level^2 * 500`.
-   **Net Worth:** The `/networth` command calculates a player's total value from their wallet, bank, and the base value of their items.
-   **Trading:** Players can securely trade characters and items with each other.

### Game Systems
-   **PvP Battles:** A turn-based or instant-resolution combat system where players fight for coins and XP.
-   **Betting:** Mini-games like coin flips where players can risk coins for a potential reward.
-   **Stealing:** A high-risk, high-reward system allowing players to steal coins from others. Success is influenced by stats and artifacts.
-   **Item System:**
    -   **Poisons:** Consumable items providing temporary buffs/debuffs for hours.
    -   **Artifacts:** Permanent, upgradable items that provide passive bonuses. The number of equippable artifacts is `floor(level / 2)`.
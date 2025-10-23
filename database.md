# Database Schema (High-level)

This document outlines collections/tables and important fields. Example uses MongoDB documents.

## collections

### users

* `_id` (ObjectId)
* `telegram_id` (number/string)
* `username` (string)
* `wallet_coins` (int)
* `bank_coins` (int)
* `level` (int)
* `xp` (int)
* `attributes` { STR, INT, DEX, AGI, DEF, VIT, LUK }
* `inventory` {
  characters: [{ character_id, obtained_at }],
  weapons: [{ item_id, equipped:boolean }],
  poisons: [{ item_id, count }],
  artifacts: [{ artifact_id, level, equipped:boolean }]
  }
* `last_steal_at` (timestamp)
* `last_bet_at` (timestamp)
* `created_at`

### characters

* `_id`
* `name`
* `anime`
* `rarity`
* `owner_id` (ref to users)
* `card_stats` (optional)
* `dropped_in_chat_id` (optional)

### items (weapons/poisons/artifacts)

* `_id`
* `type` ('weapon'|'poison'|'artifact')
* `name`
* `base_price`
* `effects` (JSON)
* `rarity`
* `global_supply` (if limited drops)
* `created_at`

### battles

* `_id`
* `player1_id`
* `player2_id`
* `winner_id`
* `loser_id`
* `player1_snapshot` (attributes & equipment)
* `player2_snapshot`
* `used_items`
* `coin_change`
* `timestamp`

### steal_logs

* `_id`
* `thief_id`
* `target_id`
* `success` (bool)
* `amount`
* `thief_before`
* `target_before`
* `artifacts_involved`
* `timestamp`

## Indexing

* Index on `users.telegram_id`
* Index on `characters.owner_id`
* Index on `battles.player1_id`, `battles.player2_id`, `timestamp`

## Storage tips

* Store active poison timers in Redis keyed by `user:poison:<poisonId>` with TTL.
* Use write-ahead logs for coin transfers to avoid race conditions.

# Battle System

Battles are resolved server-side and stored. They use player attributes, equipment, poisons, and artifacts.

## Core attributes

* STR, INT, DEX, AGI, DEF, VIT, LUK

## Combat scoring (example)

```
combat_score = STR*1.2 + DEX*1.1 + AGI*1.1 + INT*1.0 + DEF*0.9 + VIT*0.8 + LUK*0.5 + random_factor
```

* `random_factor` = uniform random between -5% and +5% of computed score.
* Apply active poison and equipped artifact modifiers before final score.

## Turn model

* Instant resolution (single formula) or simulated rounds (multiple iterations) — MVP: instant resolution.
* Winner receives:

  * Coin reward: `floor( base_reward * (winner_level/loser_level) )`
  * XP reward: based on level delta and rarity of used characters.
* Loser may lose a small percentage of wallet coins.

## Battle logs

* Store: `{id, player1_id, player2_id, winner_id, loser_id, player1_stats_snapshot, player2_stats_snapshot, used_items, timestamp, coin_change}`

## PvP fairness & anti-abuse

* Enforce cooldowns between battles.
* Prevent repeated auto-farming (limits on challenges per hour).
* For duels, require consent (challenge -> target accepts).

## UI

* Use inline buttons: `[Accept] [Decline]` for challenge; on resolution show `[Rematch] [Battle History]`.

## Implementation tips

* Use deterministic seeded RNG when simulating in test or replay mode.
* Store snapshots of stats in battle logs so future recalculations are consistent.

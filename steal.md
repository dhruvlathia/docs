# /steal Command — Mechanics & Rules

`/steal @target` lets a player attempt to steal `coin` from another player's wallet.

## Preconditions & limits

* Target must have > 0 wallet coins.
* `steal_cooldown` default = 10 minutes (tuneable).
* Daily steal attempt limit (e.g., 5/day) to prevent abuse.
* Banked coins are **not** stealable by default.
* If target has **Seal of Warding** active → steal auto-fails.

## Success chance (recommended formula)

Start: `base_chance = 50%`

Modifiers:

* Thief level factor: `(thief.level - target.level) * 0.5%` (clamped)
* Thief LUK factor: `thief.LUK * 0.2%`
* Thief offensive artifacts: sum `artifact.offense_value` (configurable)
* Target artifact defense: sum `artifact.defense_value` (e.g., Wardstone level * 6%)
* Equipped artifact level penalty: `sum(equipped_artifact.level) * 3%`

Final:

```
final_chance = clamp( base_chance + level_factor + luck_factor + thief_artifact_bonus - target_artifact_defense - equipped_levels_penalty, 5%, 95% )
```

## Stolen amount

* If success: amount = `min(target.wallet_coins, floor(random(5..25)% * target.wallet_coins))`
* If fail: thief pays penalty = `ceil( thief.wallet_coins * 0.05 )` or loses a fixed fine.
* Optionally: failed steal may trigger retaliation (instant counter-steal or log).

## Artifact interactions

* **Wardstone** reduces stolen chance (defense).
* **Aegis of Thorns** can damage thief or refund part of attempted steal on failure.
* **Lockbreaker Ring** increases success (offense).
* **Seal of Warding** grants immunity while active.

## Logging & audits

* Log every attempt: `{thief_id, target_id, timestamp, success, amount, thief_balance_before, target_balance_before, artifacts_involved}`.
* Provide `/stealhistory` for admins.

## UX

* Always show estimated success% in steal confirmation inline before executing.
* For fairness, require thief to confirm (press inline button) after success% is shown to avoid accidental attempts.
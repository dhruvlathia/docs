# Artifacts (Equipable & Upgradable)

Artifacts are persistent items that give passive bonuses or unique abilities. They can be equipped (limit = floor(level / 2)) and upgraded.

## Equip rules

* `max_equipped = floor(user.level / 2)`
* Equipping an artifact modifies the player's live stats and defensive values (used by steal/battle services).

## Upgrade model

* `upgrade_cost(level n -> n+1) = base_price * multiplier^(n-1)`
* `multiplier` recommended = 2.0
* Upgrading increases effect size and theft defense.

## Artifact list (20) — name + short effect & role

1. **Timekeeper’s Relic** — +10% poison duration & -10% poison cooldown. (Support)
2. **Crystal Pendant** — +15% XP gain. (Progression)
3. **Mirror Amulet** — Reflects % damage back to attacker. (Defense)
4. **Lucky Bell** — +2 LUK base; each level +1 LUK. (Luck)
5. **Titan Core** — +10% STR base (scales). (Offense)
6. **Phantom Cape** — +5% dodge chance (scales). (Evasion)
7. **Eternal Flame** — One revive per day (upgrade improves HP%). (Survival)
8. **Infinity Lens** — Reveal opponent stats pre-battle. (Tactical)
9. **Soul Gem** — Convert X% of dealt damage to HP. (Sustain)
10. **Aether Crown** — Extend poison durations by +30s (scales). (Support)
11. **Guardian Talisman** — Flat +DEF. (Tank)
12. **Silent Coinpurse** — +5% bank capacity (per level). (Economy)
13. **Lockbreaker Ring** — +5% steal success per level (offensive). (Thief)
14. **Wardstone** — Reduces chance of being stolen from (defensive). (Anti-steal)
15. **Seal of Warding** — Temporary toggleable anti-steal immunity. (Utility)
16. **Trade Sigil** — Reduce marketplace fees. (Economy)
17. **Battle Standard** — Small passive to all combat stats. (Buff)
18. **Haggler’s Eye** — -5% shop prices (scales). (Economy)
19. **Echo Locket** — On loss, recover small coin from opponent (tiny %). (Soft rebalance)
20. **Aegis of Thorns** — Backfires on thief on fail (damage/refund chance). (Punish)

## Artifact value accounting

* `artifact_value = base_price + sum(upgrade_costs_paid)`
* Display artifact level, base effect, and next-level upgrade cost in `/inventory` and `/shop`.

## Anti-steal interactions

* Defensive artifacts (Wardstone, Seal of Warding, Aegis) reduce steal chance or create penalties for thieves.
* Offensive artifact (Lockbreaker) increases thief chance when equipped.

## Implementation tips

* Store artifact object with `{ id, name, level, base_price, owner_id, equipped:boolean }`
* Precompute artifact_defense_value per equipped artifact for steal formula.

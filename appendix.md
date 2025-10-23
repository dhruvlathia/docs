# Appendix — Examples, formulas & tips

## Bank capacity examples

* Level 1: 1^2 * 500 = 500 coin
* Level 5: 25 * 500 = 12,500 coin
* Level 20: 400 * 500 = 200,000 coin

## Artifact upgrade example

Artifact: Lucky Bell, base_price = 1000, multiplier = 2.0

* L1 -> L2 cost = 1000
* L2 -> L3 cost = 2000
* L3 -> L4 cost = 4000
  Total to reach L4 = 7,000 coin spent on upgrades

## Steal example calculation

* base = 50%
* thief level = 10, target level = 12 => level_factor = (10-12)*0.5% = -1%
* thief LUK = 5 => +1%
* target Wardstone level 2 => defense = 12%
* final = 50 -1 +1 -12 = 38%

## Networth checklist (server side)

* wallet + bank + all inventory valuations
* Use `purchase_price + upgrades_paid` for artifacts valuation
* For market price, optionally use last-sale price as reference

## Developer tips

* Use Redis for TTL-based timed effects (poisons).
* Always persist pre-battle snapshots to prevent post-factum recalculation errors.
* Use transactions for coin transfers (MongoDB transaction or relational DB transaction).

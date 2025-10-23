# Poisons (Consumables)

Poison items are consumables stored in inventory. They are **used** to apply temporary effects, durations defined on purchase.

## Usage rules

* Poisons must be explicitly used (e.g., `/use poison_name` or via profile -> Poisons -> Use).
* Same-poison stacking: **refresh duration** instead of stacking magnitude.
* Different poisons: effects apply concurrently unless designed to conflict.
* Each poison has: `base_price`, `duration_seconds`, `effects` (stat modifiers).

## Suggested Poisons (10)

1. **Speed Venom** — Reduces betting cooldown by 5s. Duration: 180s
2. **Luck Tonic** — +5 LUK. Duration: 120s
3. **Iron Skin** — +4 DEF. Duration: 180s
4. **Shadow Mist** — +4 AGI. Duration: 180s
5. **Focus Serum** — +5 DEX (reduce miss chance). Duration: 120s
6. **Power Elixir** — +6 STR. Duration: 120s
7. **Cursed Flask** — +10% damage, -5 DEF. Duration: 180s
8. **Gamble Nectar** — +10% win chance in bets. Duration: 300s
9. **Mindstorm Brew** — +5 INT. Duration: 180s
10. **Phoenix Drop** — One-time revive with 20% HP on defeat (single use)

## Pricing & sell-back

* Set purchase price and a reduced sell-back (e.g., 25% of buy price) to discourage flipping.
* Active poisons have no sell-back until they expire.

## Implementation tips

* Keep active-poison timers in Redis with TTL for scalability.
* Show active status on `/profile` and attach durations to battle calculations.

# Weapons

Weapons are permanent equipables that improve combat stats. They can be bought or found and can be traded.

## Weapon rules

* Weapons are permanent until sold or traded.
* Weapon rarity affects stat magnitude (Common / Rare / Epic / Legendary).
* A player can have one primary weapon (or allow multiple slots per design).

## Example weapons

* **Wooden Katana** — +2 STR (Common)
* **Spirit Blade** — +4 STR, +1 AGI (Rare)
* **Shadow Dagger** — +3 DEX (Rare)
* **Mystic Staff** — +3 INT (Rare)
* **Guardian Shield** — +3 DEF (Common)

## Pricing

* Price scales with rarity; ensure rare weapons either cost a lot or appear rarely as drops.

## Integration

* Weapon bonuses are added to combat score calculations.
* Weapons do not affect steal calculations unless you introduce a weapon-based stealing mechanic.

## Implementation tips

* Store weapons as items with `base_price`, `rarity`, `stat_bonuses`.
* Allow weapon-specific cosmetic skins or card art in later versions.

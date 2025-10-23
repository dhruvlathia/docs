# Commands (User-facing)

## Primary

* `/grab <character name>`
  Claim the currently dropped character. Inline "Grab" button also available.

* `/inventory`
  Show characters, weapons, poisons, artifacts, and equipped items.

* `/profile`
  Show your profile: level, XP, core attributes, equipped items, wallet.

* `/networth @user?`
  Show full networth. If user not mentioned, shows your own.

* `/shop`
  Opens inline shop with categories: Weapons / Poisons / Artifacts / Bank.

* `/bet <amount>`
  Open betting menu for available games.

* `/battle @user`
  Challenge a user to PvP. Inline rematch and spectate options available.

* `/battlehistory @user?`
  Show paginated battle logs. Default shows recent 10.

* `/steal @user`
  Attempt to steal coins from a user — subject to cooldowns and defenses.

* `/help`
  Display commands grouped with inline buttons for each group.

## Bank commands

* `/deposit <amount>` — Deposit coins into bank.
* `/withdraw <amount>` — Withdraw coins from bank.

## Moderation & utility (admin)

* `/drop` (admin) — force a drop in a chat.
* `/balance @user` (admin) — check wallet & bank for user.
* `/setcoins @user <amount>` (admin) — set coin balance for testing.

## Inline Buttons

* On character drop: `[⚡ Grab Character] [📜 Info]`
* On shop view: `[🗡️ Weapons] [☠️ Poisons] [⚱️ Artifacts] [💰 Bank]`
* On profile: `[🎒 Inventory] [⚔️ Battle] [💸 Networth]`

## Notes

* Commands like `/grab`, `/shop`, and `/bet` are core — show as primary in `/help`.
* Use callback queries for inline actions to keep chat clean.

# Economy

## Currency

* Name: `coin`
* Used for purchases, upgrades, betting, trading, and bank transfers.

## Networth (`/networth`)

`Networth` = wallet_coins + bank_coins + inventory_value
Inventory value is computed as:

* Poisons: sum of purchase prices (active or not)
* Artifacts: base price + cumulative upgrade costs paid
* Weapons: purchase prices (or market-estimated value)
* Characters: optional valuation (rare characters may get value)

**Display example:**

```
Networth for @dhruv
- Wallet: 1,200 coin
- Bank: 4,500 coin
- Poisons: 850 coin
- Artifacts: 23,400 coin
- Weapons: 3,100 coin
TOTAL NETWORTH: 33,050 coin
```

## Bank

* Capacity formula: `bank_capacity = level^2 * 500`

  * Level 1 = 500
  * Level 10 = 50,000
  * Level 50 = 1,250,000
* Deposit and withdraw anytime.
* If a deposit exceeds the capacity, the operation fails with remaining capacity shown.

## Artifact Upgrades

* Each artifact has `base_price` and `base_effect`.
* Upgrade cost formula:

```
upgrade_cost(n -> n+1) = base_price * multiplier^(n-1)
```

* Suggested `multiplier = 2.0` (tunable).
* Artifact effect scales with artifact level (linear or percentage).
* Upgrades become exponentially expensive.

## Coin sinks

* Artifact upgrades, marketplace fees, event purchases — crucial to prevent inflation.
* Consider daily maintenance fees for very powerful artifacts.

## Economy notes

* Track total coin issuance and sinks to keep inflation stable.
* Balance drop rates, shop prices, and XP to prevent too-fast progression.

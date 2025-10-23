# Database Schema (Firebase Realtime Database)

The entire game state is stored in a Firebase Realtime Database. The structure is designed to be flat to optimize for read speeds and prevent deep nesting.

## Root Structure

```json
{
  "users": {
    "telegram_user_id_1": {
      "username": "PlayerOne",
      "level": 10,
      "xp": 3100,
      "coins": {
        "wallet": 50000,
        "bank": 250000
      },
      "attributes": {
        "str": 15, "int": 12, "dex": 14, "agi": 16, "def": 13, "vit": 18, "luk": 11
      },
      "timestamps": {
        "last_steal": 1761234567,
        "last_bet": 1761234888,
        "created": 1761100000
      }
    }
  },
  "inventories": {
    "telegram_user_id_1": {
      "characters": {
        "character_id_123": { "obtained_at": 1761200000 },
        "character_id_456": { "obtained_at": 1761210000 }
      },
      "artifacts": {
        "artifact_id_1": { "level": 2, "equipped": true },
        "artifact_id_99": { "level": 1, "equipped": false }
      },
      "poisons": {
        "poison_id_100": { "count": 5 },
        "poison_id_101": { "count": 2 }
      }
    }
  },
  "active_effects": {
    "telegram_user_id_1": {
      "poison_id_p1": { "expires_at": 1761241767 }
    }
  },
  "game_data": {
    "characters": {
      "character_id_112": { "name": "Naruto Uzumaki (Sage)", "anime": "Naruto", "rarity": "Legendary", "price": 250000, "stats": {"str": 40, "vit": 50, "agi": 30} }
    },
    "artifacts": {
      "artifact_id_100": { "name": "Amulet of Swiftness", "base_price": 5000, "description": "+5 AGI." }
    },
    "poisons": {
      "poison_id_89": { "name": "Draught of Steel", "price": 150, "duration_hours": 2, "description": "+10 DEF for 2 hours." }
    },
    "weapons": {
      "weapon_id_100": { "name": "Excalibur", "rarity": "Mythic", "price": 400000, "stats": {"str": 100, "vit": 50, "def": 20} }
    }
  },
  "battle_logs": {
    "telegram_user_id_1": {
      "log_id_1": { "opponent": "PlayerTwo", "winner": "PlayerOne", "timestamp": 1761230000 }
    }
  },
  "steal_logs": {
    "telegram_user_id_1": {
       "log_id_1": { "target": "PlayerThree", "success": true, "amount": 1250, "timestamp": 1761234567 }
    }
  }
}
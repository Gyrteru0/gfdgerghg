# Shadow Fiend Gyrteru 1v1 Bot (`v8.4.0-741f`, Patch `7.41f` — Pure Deterministic Engine, Zero ML)

Welcome to the **Shadow Fiend Gyrteru 1v1 Bot**! This bot is designed exclusively for the **1v1 Solo Mid** lobby mode in Dota 2 (`Shadow Fiend vs Shadow Fiend`, no river rune pickups per 1v1 rules).

I decided to create this project because most of the existing SF 1v1 bots were either outdated or lacked in-depth, tick-exact laning and duel logic.

🚨🚨!! IMPORTANT!! Check this image for a guide on setting up this bot: https://fotora.ru/uploaded/?ID=ZFYRP31052026165429 🚨🚨

---

## ✨ Features & Architecture (`v8.4.0-741f`)

1. **30 Hz Ballistic Last-Hit & Deny Engine (`nevermore/lasthit.lua`, `nevermore/utils.lua`):** Phase-locked creep approach, projectile/turn-rate scheduling (`24.0 deg/tick`), under-tower prep, and lethal-aware Shadowraze CS securing.
2. **Pure-Deterministic Minimax Duel Simulator + Analytical Exchange Gate (`nevermore/war_core.lua`, `nevermore/war_director.lua`, `nevermore/exchange.lua`):** Zero ML / zero stochastic noise — 30 Hz forward physics simulation of multi-coil + right-click + creep-wave + T1 tower + `25%` uphill-miss trades with exact impact-time stack expiry (`stack_rem`), lossless OOM/CD pruning, and `EXP-009` Schmitt-trigger hold-band continuity.
3. **Exact Analytic Shadowraze Dodge & Anti-Pump-Fake (`bot_nevermore.lua`, `nevermore/combat.lua`):** Zero-delay Tick-0 escape solver (`R_eff = 274u`), chain-band (`W -> E`, `E -> W -> Q`) veto, and action-preserving anti-pump-fake protection.
4. **Sub-`700u` Right-Click Anti-Abuse & Safe Behind-T1 TP (`bot_nevermore.lua`, `nevermore/positioning.lua`):** Immediate centered `Q`/`W` + auto-attack retaliation when an opponent steps inside `< 625u`, pre-CS OOM anti-oscillation disengage, `12`-step cliff passability + terrain-stall detour solver, and safe `P.GetBehindT1(bot, 520)` Return TP (`~1,380u` out of `Raze3` ambush reach).
5. **Verified `CDOTA_Bot_Script` C++ Engine Truth (`nevermore/engine_truth.lua`, `nevermore/combat.lua`, `nevermore/world.lua`):** Live `GetArmor()`, `GetAttackDamage()`, global `GetTowerAttackTarget(team, TOWER_MID_1)`, `1.00x` `Reinforced vs Hero` T1 damage (`7.31+/7.41f`), `267` L1 SF mana (`7.41e/f`), and exact `7.41f` FoW respawn countdowns (`12..100s`).
6. **Anti-AFK Lobby Economy Helper (`bot_beastmaster.lua`, `hero_selection.lua`):** Spawns 4 Beastmaster helpers on jungle XP cycles so Dota 2 does not trigger the 5-minute AFK gold redistribution spike in 1v1 lobbies.

---

## 📦 Installation (`bots/` folder)

Extract `bots.zip` so the `bots` folder sits directly at:
```text
steamapps/common/dota 2 beta/game/dota/scripts/vscripts/bots
```
(`bot_nevermore.lua` at `.../vscripts/bots/bot_nevermore.lua` and submodules in `.../vscripts/bots/nevermore/*.lua`).

---

## 🛠️ Builds (1v1 Solo Mid)

### Skill Build
* **Shadowraze (`1, 3, 5, 7`) + Presence of the Dark Lord (`2, 4, 6, 8`) + Talents + Passive Requiem (`9, 12, 18`)**.

### Item Build (`item_purchase_nevermore.lua`)
* **Starting Items:** Enchanted Mango, Faerie Fire, 2x Iron Branch, 2x Circlet, Tango, Observer Ward.
* **Core Progression:** 2x Bracer ➔ Boots of Speed ➔ Power Treads ➔ Dragon Lance ➔ Kaya (+ dynamic Healing Salve w/ Critical Salve Unlock, Enchanted Mango, Clarity, Infused Raindrop, Observer/Sentry Wards).

---

## 💬 Feedback & Support

* 📝 **GitHub:** Open an Issue right here in the repository.
* 🎮 **Steam:** https://steamcommunity.com/sharedfiles/filedetails/?id=3728369918
* 👾 **Discord:** `deleted_user_1ad51966a18d`

# Call-Of-Duty-Black-ops-2-Zombies-Plutonium-Bots-V3.0
Friendly AI teammates for Black Ops 2 Zombies on Plutonium (zmbots.iwd). The bots fill empty player slots and play Survival, co-op and Grief: they move around the map, fight, shop, open the map, revive and follow orders.
# Zombie Bots for Black Ops 2 Zombies (Plutonium T6)

Friendly AI teammates for Black Ops 2 Zombies on [Plutonium](https://plutonium.pw/). Bots fill the empty player slots and play **Survival, co-op and Grief**. They move around the map, fight, buy weapons and perks, open doors, revive teammates and follow your commands, all under the same rules as a human player.

---

## Installation

1. Press **Win + R**, paste the path below and press **Enter**:
   ```
   %localappdata%\Plutonium\storage\t6
   ```
2. Open the `mods` folder. If there isn't one, create it.
3. Copy the `zombie_bots` folder from this repository into `mods`. It contains `mod.json` and `zmbots.iwd`, so you end up with:
   ```
   %localappdata%\Plutonium\storage\t6\mods\zombie_bots\mod.json
   %localappdata%\Plutonium\storage\t6\mods\zombie_bots\zmbots.iwd
   ```
4. Start Plutonium T6 Zombies, open **Mods**, select **Zombie Bots**, then start a custom game.
5. Bots join after the opening black screen. About 6 seconds later the hint "Zombie Bots v3.0" appears, and the top-left corner shows **BOTS: WANDER**.

**Number of bots:** you get up to 7 bots, limited by the lobby size. To play with more bots, raise the **party size** in the custom game lobby (8 players maximum, humans included). You can also set `zm_bots` in the console.

**Grief:** also install a Grief fix script that splits players into two teams, for example *Grief Custom Games*. "https://forum.plutonium.pw/topic/36136/grief-custom-games-unified-fixes" The bots join the smaller team automatically.

**Using it with another mod:** drag `zmbots.iwd` into that mod's folder.

---

## Features

### Bots that play like teammates
- **Same rules as you:** the game's normal health regen, every perk bought with points, perks lost when downed, and normal gun damage.
- **Deliberate exceptions:** 500 health (1000 with Juggernog), immunity to lava, fire and other map hazards, and refilled reserve ammo. All of these can be changed.
- **Juggernog first:** it's the first perk they buy, followed by Double Tap, Speed Cola, Quick Revive, Mule Kick and the rest.
- **Wall guns:** they replace their weakest gun with a better wall weapon and never swap back to a weaker gun.
- **Mystery Box:** they use it and follow a weapon tier list to decide what to keep.
- **Pack-a-Punch** from round 10.
- **Opening the map:** they open doors and clear debris, but keep money for a gun first while they still hold starter weapons.
- **Power-ups:** they pick them up, but won't grab a Nuke while zombies are still coming, or Double Points or Insta-Kill when no zombies are left.
- **Reviving:** they revive teammates (at most two bots per downed player), guard downed players, and back off when surrounded.
- **Fighting:** they knife weakened zombies, throw grenades at large groups (never near a teammate), flee when cornered, and use shields when you have one.
- **Callouts** in the kill feed: "I'm down!", "Reviving <name>!", "Thanks for the revive!" and more.

### Commands
| Input (controller / keyboard) | Action |
| --- | --- |
| Double-tap **Dpad Down** / **2** | Cycle bot mode: stay, wander, wander further, follow |
| Double-tap **Dpad Left** / **5** | Teleport your team's bots to you |

The current mode is always shown in the top-left corner.

### Co-op and Grief
- **Co-op:** any player can command the bots. Players who join late get the controls, and the controls keep working after you bleed out.
- **Per-team control in Grief:** each team commands, teleports and gets callouts only from its own bots.
- **Team balancing in Grief:** bots join the smaller team, humans included (1 human + 7 bots = 4 vs 4), and rebalance if someone switches.
- **Teams in Grief:** bots revive and protect only their own team.
- **Griefing bots:** they're balanced so you can grief them like a player, for example by training a horde into them.

### Freeze protection
Bots never stand around doing nothing. Treyarch's own engine failsafe and a stuck check get any stuck bot moving again, without teleporting it.

---

## Console commands

Type `set bot_cmd <command>` in the Plutonium console.

| Command | Effect |
| --- | --- |
| `help` | List the commands |
| `status` | Each bot's team, health, points, weapon, kills, downs and revives |
| `diag` | Details on any stuck bot |
| `stay` / `wander` / `wander_further` / `follow` | Set this mode for every bot |
| `regroup` | Teleport the host's team's bots to the host |
| `unstick` | Reset every bot |
| `add` | Add one more bot |

## Settings (optional dvars)

| Dvar | Default | Meaning |
| --- | --- | --- |
| `zm_bots` | 7 | Number of bots |
| `zm_bots_fill` | 0 | 1 = `zm_bots` is the total team size, humans included |
| `zm_bot_default_mode` | wander | Starting mode: stay, wander, wander_further, follow |
| `bot_max_health` | 500 | Bot base health (Juggernog doubles it) |
| `bot_lava_immune` | 1 | 0 = lava, fire and hazards hurt bots |
| `bot_infinite_ammo` | 1 | 0 = bots manage ammo like a player |
| `bot_perk_round` | 8 | Round bots start buying perks |
| `bot_pap_round` | 10 | Round bots start Pack-a-Punching |
| `bot_skill` | 2 | Aim only: 1 easy, 2 normal, 3 hard |
| `bot_grenade_cluster` | 5 | Zombies needed in a group before a grenade |
| `bot_grief_balance` | 1 | Grief team balancing (0 = off) |
| `zm_bot_hud` | 1 | Mode display (0 = hidden) |
| `zm_bot_chatter` | 1 | Bot callouts (0 = off) |
| `zm_bot_hints` | 1 | Start-of-match hint (0 = off) |
| `bot_debug` | 0 | 1 = show stuck-check actions |

---

## Credits

- **RlKk01**: original GerardS0406 BySc techboy04gaming, *ZM Bots* mod for BO2 Zombies (Plutonium)
- **supergamer9787**: *Zombie Bots* v3.0: Grief fixes and team balancing, co-op fixes, player-rules balance, freeze fix, weapon and box improvements, commands, HUD and callouts

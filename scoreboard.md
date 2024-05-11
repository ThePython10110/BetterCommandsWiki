---
description: >-
  The scoreboard system is a complex gameplay mechanic utilized through
  commands. Mainly intended for mapmakers and server operators, scoreboards are
  used to track, set, and list the scores of players.
---

# Scoreboard

## Objectives

Entities can hold scores in the scoreboard specified by objective. Objectives track a number of points for entities while meeting a single criteria. Objective scores are stored as integers with the range of -99,999,999,999,999 to 100,000,000,000,000.

Objectives have two main properties: a name and a criterion. The objective's name is used internally for referencing in commands and selector arguments. And the criterion determines its behavior — primarily what to track.

Objective names must be single words containing only alphanumeric characters and underscores.

The entity's score in any objective can be changed from commands. It can be increased by, decreased by, or set to a given amount with commands.  Currently, only players are supported, and not other entities.

Objectives also have other properties to customize their appearance and behavior:

| Property     | Description                                                                                                                                                                                                                                                                                                                                    |
| ------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| displayname  | Specify the objective's display name that appears in the sidebar and as the result of some commands. By default, the objective's name is the display name.                                                                                                                                                                                     |
| numberformat | <p>Specify the objective's number format for the score. The number format can be blank, fixed, and styled.</p><p>Blank number format displays nothing on the scoreboard. Fixed number format displays the contents specified in the command.</p><p>Styled number format displays the score number with the color specified in the command.</p> |

The number format property and the score holder's name can be changed per-entity using `/scoreboard players display numberformat|name <target> ...`

## Criteria

These criteria's names consist of a single alphabetical string.

| Criteria name   | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| dummy           | Score that can be changed only by commands, and not automatically by the game. This can be used for storing integer states and variables, which then can be used with the scoreboard's operations to do arithmetic calculation.                                                                                                                                                                                                                                                                                                                                                                               |
| trigger         | Score that can be changed by commands, and not automatically by the game. The `/trigger` command can be used by players to set or increment and decrement their own score. The command fails if the objective has not been "enabled" for the player using it. If the player uses it, the objective is automatically disabled for them afterward. By default, all trigger objectives are disabled for any players. Ordinary players can use the `/trigger` command, even if cheats are disabled or if they are not server operators, in which case this is useful for safely taking non-operator player input. |
| deathCount      | Score increments automatically for a player when they die.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| playerKillCount | Score increments automatically for a player when they kill another player.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| health          | Represents the amount of health/HP the player has                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |

**Compound criteria**

Compound criteria's names are divided into parts, delimited with periods (.). For example, `killed_by.mobs_mc:zombie` is a valid compound criteria, under which player scores would increment whenever they're killed by a zombie.

<table><thead><tr><th width="315">Criteria base name</th><th>Description</th></tr></thead><tbody><tr><td><code>teamkill.&#x3C;team_color></code></td><td><p>Player scores increment when a player kills a member of the given colored team.</p><p>These criteria follow the complete format <code>teamkill.&#x3C;team_color></code>, where <code>&#x3C;team_color></code> is a valid team color.</p></td></tr><tr><td><code>killedByTeam.&#x3C;team_color></code></td><td><p>Player scores increment when killed by a member of the given colored team.</p><p>These criteria follow the complete format <code>killedByTeam.&#x3C;team_color></code>, where <code>&#x3C;team_color></code> is a valid team color.</p></td></tr><tr><td><code>killed_by.&#x3C;entity></code></td><td>Player scores increment when killed by the specified entity. <code>&#x3C;entity></code> can be any entity or <a href="entity-aliases.md">entity alias</a>, or <code>player</code>.</td></tr><tr><td><code>picked_up.&#x3C;item></code></td><td>Player scores increment when picking up the specified item. <code>&#x3C;item></code> can be any itemstring or alias, or <code>*</code> to match any item. Scores are incremented by one for each itemstack picked up, regardless of how many items are in the itemstack.</td></tr><tr><td><code>mined.&#x3C;node></code> or <code>dug.&#x3C;node></code></td><td>Player scores increment when digging the specified node. <code>&#x3C;node></code> can be any itemstring or alias, or <code>*</code> to match any node.</td></tr><tr><td><code>placed.&#x3C;node></code></td><td>Player scores increment when placing the specified node. <code>&#x3C;node></code> can be any itemstring or alias, or <code>*</code> to match any node.</td></tr><tr><td><code>crafted.&#x3C;item></code></td><td>Player scores increment when crafting the specified item. <code>&#x3C;item></code> can be any itemstring or alias, or <code>*</code> to match any item. Scores are incremented by one for each craft, regardless of how many items are crafted.</td></tr></tbody></table>

## History

| Version | Action                                                                                                 |
| ------- | ------------------------------------------------------------------------------------------------------ |
| v1.0    | Added the scoreboard, and several criteria                                                             |
| v2.0    | Added `crafted.<item>`, `dug.<node>`, `mined.<node>`, `picked_up.<item>`, and `placed.<node>` criteria |
|         |                                                                                                        |

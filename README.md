# LivingNarratives Anti-Omniscience

AI Dungeon script library for scene-scoped NPC knowledge control.

The script tracks which characters were present for conversations and injects a knowledge packet so NPCs do not act omniscient about information they did not witness or receive on-screen.

## Files

- `LivingNarratives_AntiOmniscience_AI_Dungeon_Script.txt` - full pasteable Script Library file.

## AI Dungeon Hook Wrappers

Paste the full script into one Script Library card that loads before the hooks.

Input / `onInput`:

```js
const modifier = (text) => {
  return InformationFirewall("input", text);
};
modifier(text);
```

Context / `onModelContext`:

```js
const modifier = (text) => {
  return InformationFirewall("context", text);
};
modifier(text);
```

Output / `onOutput`:

```js
const modifier = (text) => {
  return InformationFirewall("output", text);
};
modifier(text);
```

## Roster Sources

Character detection is roster-gated. The script reads valid character names from story cards typed as `character`, `npc`, `cast`, or `roster`.

If needed, add a roster marker to a story card:

```txt
[roster: Rick, Diane, Morgan Lee]
```

or:

```txt
IF_ROSTER: Rick, Diane, Morgan Lee
```

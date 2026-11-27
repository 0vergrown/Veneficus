# Veneficus (data pack)

A Harry Potter inspired data pack for Apoli and Origins. It adds a Wizard to the Class layer of the Origins: Classes data pack, as a pack of its own. A wizard carries up to eight of twenty spells, picks them in a skill tree, and casts them with a wand by clicking short patterns of left and right clicks. The spell list and most of the spell behaviour follow Hogwarts Legacy.

All ids use the `veneficus` namespace. Each spell is one power named after it, so Stupefy is `veneficus:wizard/stupefy` in `data/veneficus/powers/wizard/stupefy.json`.

## Requirements

| | Version |
| --- | --- |
| Minecraft | 1.20.1 or 1.21.1 |
| Loader | Fabric (1.20.1, 1.21.1) or NeoForge (1.21.1) |
| Apoli | 1.141.0 or newer |
| Origins | 1.53.0 or newer |
| Origins: Classes | the data pack, for the Class layer |
| Birdsong | optional, 1.0.0 or newer, for spoken incantations |
| LambDynamicLights | optional, on the client, for Lumos light that moves smoothly with you |

## Installing

The folder is both a data pack and a resource pack.

1. Put it (or a zip of it) in the world's `datapacks` folder, next to Origins: Classes.
2. Put the same folder in `resourcepacks` and enable it. It holds the wand model, the spell icons, the spell particles, the Protego bubble, the screen effects and the translations. Without it the wand is a plain stick and players see raw translation keys.

## Becoming a wizard

Pick Wizard in the Class layer. You start with a wand, a renamed stick with its own model. To make another, use an amethyst shard, a feather or a phantom membrane on a stick. Both items are used up.

Spells only work while the wand is in your main hand. While you hold it, clicks cast spells instead of breaking blocks, opening doors or hitting creatures.

## Casting

Every spell is cast with a pattern of three clicks, each one left (L) or right (R). That gives eight patterns: LLL, LLR, LRL, LRR, RLL, RLR, RRL and RRR. Each click has to come within 0.7 seconds of the one before, or the pattern starts over. A pattern with no spell on it fizzles.

The panel in the bottom right corner, beside the hotbar, shows the spells you carry, with the three runes of each pattern beside its icon. It is drawn at 75% opacity and at the same size whatever your GUI scale is, so it stays small on large screens. Patterns that start with L are in the left column and patterns that start with R in the right one. As you click, the spells that no longer match fade, so after the first click you can see which four are left. A recharging spell is shaded from the top until it is ready, and the bar along the bottom fills with practice.

Most spells are bolts. They fly from the tip of the wand to the first block or creature in the line of sight, and they land when the bolt arrives, so far targets are hit a moment later than near ones.

Press Pick Block (middle click) with the wand in hand to open the spellbook wheel. It shows your eight patterns and the spell on each. Pick a pattern, then pick a spell in the second wheel, to bind that spell to that pattern. If the spell was already on another pattern, the two patterns swap.

## Learning spells

The Spellbook tab of the skill tree screen (`key.apoli.skill_tree`) holds every spell, in three branches: Charms (Everyday, Defensive and Offensive), Transfiguration, and the Dark Arts (Jinxes, Curses and the Unforgivable Curses). Basic Cast and Lumos are free. The others cost spell points.

A learned spell goes on the first free pattern, and a message tells you which one. You can carry eight spells, so the tree won't sell you a ninth. Shift-click a spell in the tree to forget it, which gives its points back and frees its pattern for the next spell you learn.

Spell points come from practice. Each spell that lands on a creature, and each blow or projectile that Protego turns aside, counts once, at most once every 1.5 seconds. Every 25 earns a point.

## Spoken incantations

With Birdsong installed on the server and on your client, saying a spell's incantation casts it, the same as its pattern. The wand still has to be in your hand. Speech is recognised offline on your own computer, and Simple Voice Chat isn't needed. Say "Nox" to put out Lumos. The Altering Spell and Basic Cast have no incantation. Without Birdsong the spoken triggers load switched off and the clicks work as usual.

## The spells

| # | Spell | Kind | Cost | Recharge | What it does |
| --- | --- | --- | --- | --- | --- |
| 1 | Basic Cast | Essential | 0 | 0.5 s | A bolt of red sparks: 3 damage and a push. |
| 2 | Lumos | Charm | 0 | 0.5 s | Lights the wand tip and the ground around you, and you hold the wand up. The light follows you, and with LambDynamicLights it also glides with you instead of moving a block at a time. Cast it again, or say Nox, to put it out. |
| 3 | Alohomora | Charm | 1 | 1 s | Opens or closes the door, trapdoor or fence gate it hits, iron ones too. |
| 4 | Revelio | Charm | 1 | 15 s | For ten seconds, creatures and players glow through walls and ores within 16 blocks show through the ground, coloured by kind. Anything disguised within 16 blocks loses its disguise. |
| 5 | Accio | Charm | 1 | 2 s | Pulls the creature it hits to you, with any loose items near it. A target more than 12 blocks away is brought to three blocks in front of you. |
| 6 | Wingardium Leviosa | Charm | 1 | 5 s | Lifts the target and keeps it floating for four seconds. Items and other objects float too. Cast it looking straight down to lift yourself. |
| 7 | Protego | Charm | 1 | 10 s | A shield bubble for three seconds. Bolts that hit it fly back at their caster, projectiles bounce off, and blows deal no damage and push the attacker away. |
| 8 | Finite Incantatem | Charm | 1 | 5 s | Ends spells and curses on the target, puts out fire and breaks a Protego shield. Cast it looking straight down to free yourself. |
| 9 | Expelliarmus | Charm | 1 | 6 s | Knocks the item out of the target's main hand and sends it flying to you. |
| 10 | Stupefy | Charm | 1 | 5 s | Knocks the target off its feet and stuns it for four seconds (2.5 against players). |
| 11 | Arresto Momentum | Charm | 1 | 6 s | Slows everything in a cone in front of you: creatures crawl and fall slowly, and arrows and items hang in the air. Looking down or falling, it breaks your own fall. |
| 12 | Depulso | Charm | 1 | 3 s | Blasts the target and the loose items near it far away from you. |
| 13 | Incendio | Charm | 1 | 4 s | A short jet of flame that sets creatures and blocks alight and lights campfires and candles. |
| 14 | Bombarda | Charm | 2 | 8 s | An explosion where the bolt lands that breaks blocks. Players within eight blocks are dazzled, the caster included. |
| 15 | Altering Spell | Transfiguration | 1 | 1 s | Changes a block or a creature: the next colour of wool, carpet, concrete, terracotta or glass, the next facing of a block that can turn, one step of growth for a plant, or the next variant of a sheep, horse, cat, wolf, fox, frog, parrot, axolotl, rabbit, llama, mooshroom or villager. |
| 16 | Flipendo | Jinx | 1 | 4 s | Throws the target backwards, head over heels. |
| 17 | Petrificus Totalus | Curse | 2 | 7 s | Binds the target stiff for five seconds (three against players), and it topples over. |
| 18 | Confringo | Curse | 2 | 7 s | A burning bolt that explodes where it lands. The explosion doesn't break blocks. |
| 19 | Crucio | Unforgivable Curse | 3 | 30 s | Five seconds of torment: a point of damage every half second. A player's screen splits, smears and warps as it goes on. Protego can't stop it. |
| 20 | Avada Kedavra | Unforgivable Curse | 3 | 60 s | The Killing Curse. Kills almost anything it hits, and Protego can't stop it. Casting it leaves you weakened for eight seconds. |

## Effects

The curses and charms put these effects on their targets, and Finite Incantatem clears all of them.

| Effect | From | What it does |
| --- | --- | --- |
| Petrified | Petrificus Totalus | No movement, no keys, no looking around. The body locks stiff and falls flat. |
| Stunned | Stupefy | No movement or keys, and the target lies down. A player's screen goes dark. |
| Levitated | Wingardium Leviosa | No gravity and slow drifting, and no fall damage when it ends. |
| Cruciatus | Crucio | Damage over time, slowness and no sprinting. The body writhes, and a player's screen gets worse every second. |
| Flipped | Flipendo | A full backward somersault. |
| Dazzled | Bombarda | A white flash across the screen. |

Creatures under Petrified or Stunned lose their AI until the effect ends.

## Notes

- The Altering Spell changes creature variants with commands, because Apoli has no action that edits a variant. Apoli runs these commands itself, so they work whatever the server's command settings are.
- The casting poses raise the right arm, so a left-handed player holds the wand in the left hand while the right arm moves.
- In first person, a left click dips the wand like any other attack swing.
- Iron doors and iron trapdoors open for Alohomora without redstone.

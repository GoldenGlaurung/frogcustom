This is the repository housing my changes to Frogcomposband. Whether this repository eventually becomes named "GoldenFrogcomposnand" or something equally ridiculous is yet to be decided.

I love game design in all its mediums, from tabletop to video games. My reasons for making a fork of Frog (and not another 'band or roguelike entirely) are twofold:
1) I really like most of the stuff unique to Frog. It's the most robust 'band that I've played in a while and it's got charm aplenty. The features (mainly spells, races, and monsters) that I have planned will complement what's already here nicely.
2) There's a lot of references--joke monsters, mechanics, pretty much the entirety of Zangband--that I don't get. I'd love to replace them with my own (attempt at) humor and references that I'm fairly sure few others on the planet will get.
  But since I'm a big Tolkien buff, a lot of my flavor-changes will center on that. I think it would be nice to return to Moria's/Angband's (deep, frost-unweathered) roots.
(Unofficial third reason: I *really* like frogs.)

As for point #2, yes I know there's the old versions of ToME or UnAngband I could have forked that have a heavier Tolkien presence... but hey, I tried. Couldn't get them to compile. So here we are :)

Compiling the game
Here's the steps that worked for me. (I use Windows and know shamefully little about other operating systems, so go check the readme.old.txt for those instructions. And good luck.)

1. Download the MinGW install manager at https://sourceforge.net/projects/mingw/
2. MinGW Installation Manager will automatically run. If you can help it, don't install MinGW to D:/etc... there's some hardcoded paths in the toolkit.
    a. Select components to install:
        mingw-developer-toolkit
        mingw32-base
        msys-base
    b. Installation->Apply Changes  (this will install the components of mingw)
3. Find msys.bat where you installed mingw and run it. On my box it's C:\MinGW\msys\1.0\msys.bat. This is a unix-style command shell.
4. Using the msys shell, cd to your cloned source repo. Then enter the following commands:
5. autogen.sh
6. configure --enable-win
7. make
8. Move Frogcomposband.exe file from /src to the root directory of the game. (I'll remove the need for this step one day...)

Frogcomposband's original readme.txt has been preserved as "readme.old.txt". Read it for the other instructions, disclaimers, and whatnot.


Project Goals:

Races/Classes/Personalities
* Planned Removals
  Amberite: redundant (stat-wise) when there's Dunedain right there, and I'm not big on the lore.
  Kutar and Snotling: Joke creatures that really don't fit the atmosphere I'm going for.
  Android: Like above, but I'm on the fence about them because of their unique mechanics.
  Sexy: ???
  Rage-Mage: I don't like the concept personally, and the current implementation feels a bit hacky.
* Planned additions:
  Veteran (personality): Starts with extra XP and a trusty sword that can be upgraded at higher levels.
  Arrogant (personality): Possible replacement for Sexy.
  Half-elf (race): Where did they go? Who deleted them?? I just wanna talk, I promise.
  Pseudo-Dragon (Draconite subrace): AKA the lower-XP-penalty option. But also because I love Pseudo-dragons, and breathing Light/Dark sounds badass.
  Rockmen (race): Because every game needs a mineral-related subrace. Subraces (each a different mineral) would all have different powers.
  Frog-people (race): See unofficial third reason. Gets powers to do a terrifying croak, jump, and apply poison brand to their weapon for a while.
  Chef (class): Gotta do something with all those corpses lying around. Also partly inspired from a tabletop campaign.
  Gemstone Warlock (class): From a tabletop campaign. Made a pact with a sentient stone. Shiny.
* Planned tweaks:
  Demigods: see Mechanics - Piety and Prayer. Also a candidate for removal if I'm not satisfied with how that goes.
  Clerics: see Mechanics - Piety and Prayer.
  Hybrid classes: a lot of these are in a weird place. For a few of them, I could see their XP penalty increasing along with some melee/ranged buffs. Others, I'm not sure what I'll do...

Spells
* I want to make the Arcane school suck less. It should be the pinnacle of spellcraft, not the chump school that Warrior-Mages get as a penalty.
  Replace Resist X, Resist Y... with the spell "Absorb Elements", a very short-duration fire-cold-acid-lightning resist that restores a bit of mana when hit by a resisted effect.
  Add the spell "Mirror Image" which grants a substantial boost to AC that decays rapidly when it successfully causes attacks to miss.
  Give Phlogiston interactivity with non-fueled lights: a temporary +radius effect.
  Give the spell Dimension Door.
  Add the spell "Blade of Disaster" (which summons a Hellblade pet--extra cool if it can be interacted with to wield in melee or something)
* Give schools a common mid-level dungeon book. I have the worst luck finding the right books, and then when I do, some nasty critter comes along and burns them up. This won't fix that problem, but it will make midgame casting a bit less boxed-in for some classes.

Monsters
* Add more player-monster interactions. Throw food at hounds to pacify them? Sure, why not. Bless a Potion of Water and hurl it to turn undead? Sounds dope.
* Hostile Rockmen, rock monsters, etc... I'm surprised that, for a game where you spend most of your time in dungeons, there aren't more subterranean-themed baddies.
* Tweak AI behaviors around summoning, teleporting, and healing. Give monsters some more fun self-buffs instead of filling the screen or running away.
* I'm honestly impressed by the existing array of monsters. I might add a few weaker variants of existing stronger monsters to make the early game more exciting, but not much more than that.
* Add a birth option to ban certain joke monsters (like in ToME).

Dungeons
* I'm a sucker for themed dungeons, so I'll probably add a few of those (Paths of the Dead for sure, others maybe).
* Temples (for god quests, see Mechanics - Piety and Prayer).

Mechanics
* Piety and Prayer! Call forth the Valar from the West and give players yet another option when creating a character.
  My currently planned implementation for this is that each successful god quest grants a single power-like prayer castable with Piety, a seperate pool from mana.

Misc
* Make scrolls of Inventory Protection more common and increase the upper limit that blacksmiths/scrolls can improve the to-hit/to-dam/armor bonus of gear. Attrition's a big ouchie.
* Give wands, rods, and thrown items the ability to target '5' (self).
  This would require the renaming and rebalancing of a few wands like "Heal Monster", "Haste Monster", etc... to just "Heal", "Haste", etc...
  This could mean, for example, a wand of Stone to Mud could be pointed down to dig a pit trap. For whatever reason. Or a potion could be thrown on the ground to affect your mount--no wall needed!
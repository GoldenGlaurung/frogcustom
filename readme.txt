This is the repository housing my changes to Frogcomposband. Whether this repository eventually becomes named "GoldenFrogcomposnand" or something equally ridiculous is yet to be decided.

This is a passion project. I love game design in all its mediums, from tabletop to video games. I chose to make a fork of Frog (and not, say, another 'band or roguelike entirely) are twofold:
1) I really like most of the stuff unique to Frog. It's the most robust 'band that I've played in a while and it's got charm aplenty. The features (mainly spells, races, and monsters) that I have planned will complement what's already here nicely.
2) There's a lot of references--joke monsters, mechanics, pretty much the entirety of Zangband--that I don't get. I'd love to replace them with my own (attempt at) humor and references that I'm fairly sure few others on the planet will get.
  But since I'm a big Tolkien buff, a lot of my flavor-changes will center on that. I think it would be nice to return to Moria's/Angband's (deep, frost-unweathered) roots.

As for point #2, yes I know there's the old versions of ToME or UnAngband I could have forked... but hey, I tried. Couldn't get them to compile. So here we are :)


Project Goals:
Races/Classes/Personalities
* Planned Removals
  Amberite: redundant (stat-wise) when there's Dunedain right there, and I'm not big on the lore.
  Sexy: ???
  Rage-Mage: I don't like the concept personally, and the code is littered with hacks to make it work.
  Android, 
* Planned additions:
  Veteran (personality): Starts with extra XP and a trusty sword that can be upgraded at higher levels.
  Half-elf (race): Where did they go? Who deleted them?? I just wanna talk, I promise.
  Pseudo-Dragon (Draconite subrace): AKA the lower-xp-penalty option. But also because I love Pseudo-dragons, and breathing Light/Dark sounds badass.
  Gemstone Warlock (class): From a tabletop campaign. Shiny.
  Rockmen (Dwarf subrace): Because every game needs a mineral-related subrace.
  Chef (class): Gotta do something with all those corpses lying around (also from a tabletop campaign).
* Planned tweaks:
  Demigods: see Mechanics. Also a candidate for removal if I'm not satisfied with how that goes.
  Clerics: see Mechanics.
  Hybrid classes: a lot of these are in a weird place. For a few of them, I could see their XP penalty increasing along with some melee/ranged buffs. Others, I'm not sure what I'll do...

Spells
* Make Arcane suck less. It should be the pinnacle of spellcraft, not the chump school that Warrior-Mages get as a penalty. I'll replace some of the weaker spells and buff some of the existing ones.
  Replace Resist X, Resist Y... with the spell "Absorb Elements", a very short-duration fire-cold-acid-lightning resist that restores a bit of mana when hit by a resisted effect.
  Add the spell "Mirror Image", a substantial boost to AC that decays rapidly when it causes attacks to miss.
  Give Phlogiston interactivity with non-fueled lights: a temporary +radius effect.
  Give the spell Dimension Door.
  Add the spell "Blade of Disaster" (which summons a Hellblade pet--extra cool if it can be interacted with to wield in melee or something)
* Give schools a common mid-level dungeon book. I have the worst luck finding the right books, and then when I do, some nasty critter comes along and burns them up. This won't fix that problem, but it will make midgame casting a bit less boxed-in for some classes.

Monsters
* Add more player-monster interactions. Throw food at hounds to pacify them? Sure, why not. Bless a Potion of Water and hurl it to turn undead? Sounds dope.
* Tweak AI behaviors around summoning, teleporting, and healing. Give monsters some more fun self-buffs instead of filling the screen or running away.
* I'm honestly impressed by the existing array of monsters. I might add a few weaker variants of existing stronger monsters to make the early game more exciting, but not much more than that.
* Add a birth option to ban/allow certain joke monsters (like in ToME)

Dungeons
* I'm a sucker for themed dungeons, so I'll probably add a few of those (Paths of the Dead for sure, others maybe)
* Temples (for god quests, see Mechanics)

Mechanics
* Piety and Prayer! Call forth the Valar from the West and give players yet another option when creating a character.
  My currently planned implementation for this is that each successful god quest grants a single power-like prayer castable with Piety, a seperate pool from mana.



As for compiling this game, here's the steps that worked for me. (I use Windows and know shamefully little about other operating systems, so go check the readme.old.txt for those instructions. And good luck.)

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


Frogcomposband's original readme.txt has been preserved as "readme.old.txt". Go read it for the other instructions, disclaimers, and whatnot.
# Reddit collection

Copied from [this thread](https://www.reddit.com/r/Roll20/comments/bakuwn/collection_of_roll20_macros/)

## Party Stats Macros

Be sure to replace "PC 1, PC 2" etc... with your character names!

### Party Health Check
```roll20
/w gm &{template:default} {{name=Health Check}} {{PC 1= AC @{PC 1|ac} | HP @{PC 1|hp} / @{PC 1|hp|max}}} {{PC 2= AC @{PC 2|ac} | HP @{PC 2|hp} / @{PC 2|hp|max}}} {{PC 3= AC @{PC 3|ac} | HP @{PC 3|hp} / @{PC 3|hp|max}}} {{PC 4= AC @{PC 4|ac} | HP @{PC 4|hp} / @{PC 4|hp|max}}} {{PC 5= AC @{PC 5|ac} | HP @{PC 5|hp} / @{PC 5|hp|max}}}
```

### Party Passive Perception
```roll20
/w gm &{template:default} {{name=Passive Perception Check}} {{PC 1= PP @{PC 1|passive_wisdom}}} {{PC 2= PP @{PC 2|passive_wisdom}}} {{PC 3= PP @{PC 3|passive_wisdom}}} {{PC 4= PP @{PC 4|passive_wisdom}}} {{PC 5= PP @{PC 5|passive_wisdom}}}
```

### Player Status Macro
```roll20
/w gm &{template:default} {{name=@{selected|character_name} Status}} {{Armor Class= @{selected|ac}}} {{HP= @{selected|hp} / @{selected|hp|max}}} {{Passive Perception= @{selected|passive_wisdom}}} {{Speed= @{selected|speed}}} {{Inspiration= @{selected|inspiration}}} {{Weight= @{selected|weighttotal} / [[@{selected|strength}*15]]}} {{$ (in GP) = [[@{selected|gp}+floor(@{selected|sp} / 10)+floor(@{selected|cp} / 100)+floor(@{selected|pp} * 10)+floor(@{selected|ep} / 2)]]}}
```

## Player Action Macros

### Initiative
```roll20
@{selected|wtype}&{template:simple} {{rname=**@{selected|character_name}**
ROLLS INITIATIVE!}} {{mod=@{selected|initiative_bonus}}} {{r1=[[@{selected|initiative_style}+@{selected|initiative_bonus}@{selected|pbd_safe}[INIT] &{tracker}]]}} {{normal=1}} @{selected|charname_output}
```

### Perception
```roll20
@{selected|wtype}&{template:simple} {{rname=^{perception-u}}} {{mod=@{selected|perception_bonus}}} {{r1=[[@{selected|d20}+@{selected|perception_bonus}@{selected|pbd_safe}]]}} @{selected|rtype}+@{selected|perception_bonus}@{selected|pbd_safe}]]}} {{global=@{selected|global_skill_mod}}} @{selected|charname_output}
```

## Skill mods with Descriptions / GIFS

### Initiative with custom message and GIF 
```roll20
@{selected|wtype}&{template:atk} {{rname=^{init-u}}} {{mod=@{selected|initiative_bonus}}} {{r1=[[@{selected|initiative_style}+@{selected|initiative_bonus}@{selected|pbd_safe}[INIT] &{tracker}]]}} {{normal=1}} @{selected|charname_output} {{desc= Add some text or an image here. 
[Text here, doesn't matter for images](https://media.tenor.com/images/c6b3a9b03ca4bb0563a93a75062eeecd/tenor.gif)}}
```

### Stealth w/ GIF

```roll20
@{selected|wtype}&{template:atk} {{rname=^{stealth-u}}} {{mod=@{selected|stealth_bonus}}} {{r1=[[@{selected|d20}+@{selected|stealth_bonus}@{selected|pbd_safe}]]}} @{selected|rtype}+@{selected|stealth_bonus}@{selected|pbd_safe}]]}} {{global=@{selected|global_skill_mod}}} @{selected|charname_output} {{desc= [text](https://cdn.dribbble.com/users/1055986/screenshots/3435136/ninja.gif)}}
```

## NPC Stat Macros

### NPC Stats (and roll hit dice for variable HP)

```roll20
/w gm &{template:default} {{name=Stats}} {{Armor Class= @{selected|npc_AC} (@{selected|npc_actype})}} {{Hit Dice= @{selected|npc_hpformula} | [[@{selected|npc_hpformula}]]}} {{Speed= @{selected|npc_speed}}} {{Senses=@{selected|npc_senses}}}
```

### NPC Damage Resistance and Vulnerabilities

```roll20
/w gm &{template:default} {{name= @{selected|character_name} DR/Immunities}} {{Damage Resistance= @{selected|npc_resistances}}} {{Damage Vulnerability= @{selected|npc_vulnerabilities}}} {{Damage Immunity= @{selected|npc_immunities}}} {{Condition Immunity= @{selected|npc_condition_immunities}}}
```

## NPC Action Macros

### Simple NPC Initiative
```roll20
%{selected|npc_init}
```

### NPC Perception
```roll20
@{Selected|wtype}&{template:npc} @{Selected|npc_name_flag} {{rname=^{perception}}} {{mod=@{Selected|npc_perception}}} {{r1=[[@{Selected|d20}+@{Selected|npc_perception}]]}} @{Selected|rtype}+@{Selected|npc_perception}]]}} {{type=Skill}}
/w gm &{template:default} {{name=@{selected|character_name}}} {{Passive Perception= @{Selected|passive_wisdom}}}
```

### NPC Saving Throws
```roll20
/w gm &{template:default} {{name= @{selected|character_name} Saving Throws}}  {{Str=[[@{selected|d20}+(@{selected|strength_save_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_str_save}*@{selected|npc})]] | [[@{selected|d20}+(@{selected|strength_save_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_str_save}*@{selected|npc})]]}} {{Dex=[[@{selected|d20}+(@{selected|dexterity_save_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_dex_save}*@{selected|npc})]] | [[@{selected|d20}+(@{selected|dexterity_save_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_dex_save}*@{selected|npc})]]}} {{Con=[[@{selected|d20}+(@{selected|constitution_save_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_con_save}*@{selected|npc})]] | [[@{selected|d20}+(@{selected|constitution_save_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_con_save}*@{selected|npc})]]}} {{Int=[[@{selected|d20}+(@{selected|intelligence_save_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_int_save}*@{selected|npc})]] | [[@{selected|d20}+(@{selected|intelligence_save_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_int_save}*@{selected|npc})]]}} {{Wis=[[@{selected|d20}+(@{selected|wisdom_save_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_wis_save}*@{selected|npc})]] | [[@{selected|d20}+(@{selected|wisdom_save_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_wis_save}*@{selected|npc})]]}} {{Cha=[[@{selected|d20}+(@{selected|charisma_save_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_cha_save}*@{selected|npc})]] | [[@{selected|d20}+(@{selected|charisma_save_bonus}@{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_cha_save}*@{selected|npc})]]}}
```

## Skills / Mod variable names for Macros

| stat | stat_mod | stat_\(save\)_bonus |
|---|---|---|
| strength | strength_mod | strength_save_bonus |
| dexterity | dexterity_mod | dexterity_save_bonus |
|   | > | acrobatics_bonus |
|   | > | sleight_of_hand_bonus |
|   | > | stealth_bonus |
| constitution | constitution_mod | constitution_save_bonus |
| intelligence | intelligence_mod | intelligence_save_bonus |
|   | > | arcana_bonus |
|   | > | history_bonus |
|   | > | investigation_bonus |
|   | > | nature_bonus |
|   | > | religion_bonus |
| wisdom | wisdom_mod | wisdom_save_bonus |
|   | > | animal_handling_bonus |
|   | > | insight_bonus |
|   | > | medicine_bonus |
|   | > | perception_bonus |
|   | > | survival_bonus |
| charisma | charisma_mod | charisma_save_bonus |
|   | > | deception_bonus |
|   | > | intimidation_bonus |
|   | > | performance_bonus |
|   | > | persuasion_bonus |

| desc | attribute | special |
|---|---|---|
| proficiency bonus | pb | pdb_safe |
| armour class | ac |   |
| initiative bonus | initiative_bonus |  |
| passive wisdom | passive_wisdom |   |
| movement speed | speed |  |
| hit points | hp | hp\|max |
| temp hit points | hp_temp |   |
| hit dice | hit_dice | hit_dice\|max |
| hit die type | hitdietype |   |
| carry weight | weighttotal |   |
| spell save / attack | spell_save_dc | spell_attack_bonus |

## Additional contributions (dustnite)

### On the fly dynamic lighting:
This macro is used in conjunction with TokenMod API which requires a Pro account with roll20. 

```roll20
!token-mod --set ?{Vision|Torch, light_radius#40 light_dimradius#20 light_hassight#yes light_angle#360 light_otherplayers#yes|Hooded Lantern, light_radius#60 light_dimradius#30 light_hassight#yes light_angle#360 light_otherplayers#yes|Bullseye Lantern, light_radius#120 light_dimradius#60 light_angle#60 light_hassight#yes light_otherplayers#yes|Lamp, light_radius#30 light_dimradius#15 light_hassight#yes light_angle#360 light_otherplayers#yes|Candle, light_radius#5 light_dimradius#=0 light_hassight#yes light_angle#360 light_otherplayers#yes|Darkvision, light_radius#60 light_dimradius#=-5 light_hassight#yes light_angle#360 light_otherplayers#no|Darkvision (90'), light_radius#90 light_dimradius#=-5 light_hassight#yes light_angle#360 light_otherplayers#no|Darkvision (120'), light_radius#120 light_dimradius#=-5 light_hassight#yes light_angle#360 light_otherplayers#no|Warlock Devil's Sight, light_radius#120 light_dimradius#=120 light_hassight#yes light_angle#360 light_otherplayers#no|No light source(Dusk), light_radius#120 light_dimradius#=-5 light_hassight#yes light_angle#360 light_otherplayers#no|Fog, light_radius#200 light_dimradius#=5 light_hassight#yes light_angle#360 light_otherplayers#no|No light source, light_radius#10 light_dimradius#=-5 light_hassight#yes light_angle#360 light_otherplayers#no|Blinded, light_hassight#no light_angle#360 light_otherplayers#no|Flametongue Weapon, light_radius#40 light_dimradius#40 light_hassight#yes light_angle#360 light_otherplayers#yes|Sun Blade, light_radius#30 light_dimradius#30 light_hassight#yes light_angle#360 light_otherplayers#yes}
```
### Generic Roller
```roll20
?{Roll|Public, |To-DM,/w gm} Rolling ?{Number|1}?{Type|D20|D4|D6|D8|D12|D100}+?{Modifier|0}: [[ ?{Number}?{Type} + ?{Modifier}]]
```

### Whisper to DM

```roll20
/w gm ?{Message}
```

### QuickCalc

```roll20
= [[?{Calculator}]]
```

### Trait

```roll20
/w gm &{template:npcaction} {{name=@{selected|npc_name}}} {{rname=@{selected|repeating_npctrait_$0_name}}} {{description=@{selected|repeating_npctrait_$0_desc}}} /w gm &{template:npcaction} {{name=@{selected|npc_name}}} {{rname=@{selected|repeating_npctrait_$1_name}}} {{description=@{selected|repeating_npctrait_$1_desc}}} /w gm &{template:npcaction} {{name=@{selected|npc_name}}} {{rname=@{selected|repeating_npctrait_$2_name}}} {{description=@{selected|repeating_npctrait_$2_desc}}}
```

### NPC-Attack-Legacy

```roll20
/w gm %{selected|repeating_npcaction_$0_npc_action} /w gm %{selected|repeating_npcaction_$1_npc_action} /w gm %{selected|repeating_npcaction_$2_npc_action} /w gm %{selected|repeating_npcaction_$3_npc_action}
```

### NPC-Attack

```roll20
/w gm @{selected|repeating_npcaction_$0_name} | @{selected|repeating_npcaction_$1_name} | @{selected|repeating_npcaction_$2_name}
```

### NPC-Legendary-Overview-Legacy

```roll20
Legendary Macro: /w gm @{selected|wtype}&{template:npcaction} {{name=@{selected|npc_name}}} {{rname=Legendary Actions}} {{description=The @{selected|npc_name} can take @{selected|npc_legendary_actions} legendary actions, choosing from the options below. Only one legendary option can be used at a time and only at the end of another creature's turn. The @{selected|npc_name} regains spent legendary actions at the start of its turn.}} @{selected|charname_output}
```

### NPC-Legendary-Actions

```roll20
/w gm @{selected|repeating_npcaction-l_$0_name} | @{selected|repeating_npcaction-l_$1_name} | @{selected|repeating_npcaction-l_$2_name} | @{selected|repeating_npcaction-l_$3_name}
```

### Reaction:

```roll20
/w gm &{template:npcaction} {{name=@{selected|npc_name}}} {{rname=Reaction}} {{description=@{selected|repeating_npcreaction_$0_desc} }}
```

### Spells Listing (spellslots OR innate casting)
```roll20
%{selected|repeating_spell-cantrip_$0_spell} %{selected|repeating_spell-1_$0_spell} %{selected|repeating_spell-2_$0_spell} %{selected|repeating_spell-3_$0_spell} %{selected|repeating_spell-4_$0_spell} %{selected|repeating_spell-5_$0_spell} %{selected|repeating_spell-6_$0_spell} %{selected|repeating_spell-7_$0_spell} %{selected|repeating_spell-8_$0_spell} %{selected|repeating_spell-9_$0_spell}
```

### NPC Spellbook

(This will error anytime a spell isn't available. So I made it an action)
```roll20
/w gm &{template:default} {{name=@{selected|character_name} Spellcasting}} {{DC = @{selected|spell_save_dc}}} {{To Hit = +@{selected|spell_attack_bonus} }} {{Cantrips = @{selected|repeating_spell-cantrip_$0_spellname} @{selected|repeating_spell-cantrip_$1_spellname} @{selected|repeating_spell-cantrip_$2_spellname} }} {{1st = @{selected|repeating_spell-1_$0_spellname} @{selected|repeating_spell-1_$1_spellname} @{selected|repeating_spell-1_$2_spellname} @{selected|repeating_spell-1_$3_spellname} }} {{2nd = @{selected|repeating_spell-2_$0_spellname} @{selected|repeating_spell-2_$1_spellname} @{selected|repeating_spell-2_$2_spellname} @{selected|repeating_spell-2_$3_spellname} }} {{3rd = @{selected|repeating_spell-3_$0_spellname} @{selected|repeating_spell-3_$1_spellname} @{selected|repeating_spell-3_$2_spellname} @{selected|repeating_spell-3_$3_spellname} }} {{4th = @{selected|repeating_spell-4_$0_spellname} @{selected|repeating_spell-4_$1_spellname} @{selected|repeating_spell-4_$2_spellname} @{selected|repeating_spell-4_$3_spellname} }} {{5th = @{selected|repeating_spell-5_$0_spellname} @{selected|repeating_spell-5_$1_spellname} @{selected|repeating_spell-5_$2_spellname} @{selected|repeating_spell-5_$3_spellname} }} {{6th = @{selected|repeating_spell-6_$0_spellname} @{selected|repeating_spell-6_$1_spellname} @{selected|repeating_spell-6_$2_spellname} @{selected|repeating_spell-6_$3_spellname} }} {{7th = @{selected|repeating_spell-7_$0_spellname} @{selected|repeating_spell-7_$1_spellname} @{selected|repeating_spell-7_$2_spellname} @{selected|repeating_spell-7_$3_spellname} }} {{8th = @{selected|repeating_spell-8_$0_spellname} @{selected|repeating_spell-8_$1_spellname} @{selected|repeating_spell-8_$2_spellname} @{selected|repeating_spell-8_$3_spellname} }} {{9th = @{selected|repeating_spell-9_$0_spellname} @{selected|repeating_spell-9_$1_spellname} }}
```

### Legendary Macro

```roll20
/w gm @{selected|wtype}&{template:npcaction} {{name=@{selected|npc_name}}} {{rname=Legendary Actions}} {{description=The @{selected|npc_name} can take @{selected|npc_legendary_actions} legendary actions, choosing from the options below. Only one legendary option can be used at a time and only at the end of another creature's turn. The @{selected|npc_name} regains spent legendary actions at the start of its turn.}} @{selected|charname_output}
```

### Legendary Actions

```roll20
/w gm %{selected|repeating_npcaction-l_$0_npc_action} /w gm %{selected|repeating_npcaction-l_$1_npc_action} /w gm %{selected|repeating_npcaction-l_$2_npc_action}
```

### Saves

```roll20
/w gm &{template:default} {{name=Saving Throws}} {{Str Save= [[1d20+@{selected|npc_str_save}]] | [[1d20+@{selected|npc_str_save}]]}} {{Dex Save= [[1d20+@{selected|npc_dex_save}]] | [[1d20+@{selected|npc_dex_save}]]}} {{Con Save= [[1d20+@{selected|npc_con_save}]] | [[1d20+@{selected|npc_con_save}]]}} {{Int Save= [[1d20+@{selected|npc_int_save}]] | [[1d20+@{selected|npc_int_save}]]}} {{Wis Save= [[1d20+@{selected|npc_wis_save}]] | [[1d20+@{selected|npc_wis_save}]]}} {{Cha Save= [[1d20+@{selected|npc_cha_save}]] | [[1d20+@{selected|npc_cha_save}]]}}
```

### DR/Immunities

```roll20
/w gm &{template:default} {{name=DR/Immunities}} {{Damage Resistance= @{selected|npc_resistances}}} {{Damage Vulnerability= @{selected|npc_vulnerabilities}}} {{Damage Immunity= @{selected|npc_immunities}}} {{Condition Immunity= @{selected|npc_condition_immunities}}}
```

### Perception

```roll20
/w gm &{template:default} {{name=Perception Check}} {{Perception= [[1d20+@{selected|npc_perception}]] | [[1d20+@{selected|npc_perception}]]}} {{Senses=@{selected|npc_senses}}}
```

### Stats

```roll20
/w gm &{template:default} {{name=Stats}} {{Armor Class= @{selected|npc_AC} @{selected|npc_actype}}} {{Hit Dice= @{selected|npc_hpformula} | [[@{selected|npc_hpformula}]]}} {{Speed= @{selected|npc_speed}}} {{Senses=@{selected|npc_senses}}}
```

## Additional contributions (MarkOfTheDragon)
Note: If any of the "dropdown" are created as actual standalone MACROS instead of "Abilities" on a sheet, they will break if you open that macro again, due to the HTML replacement code. To modify those, you need to re-paste the updated macro text.

### GameNotice

```roll20
&{template:atkdmg} {{desc=**Game Notice**
?{Text?}}}
```

### Maths are Hard

```roll20
&{template:atkdmg} {{desc=**Maths Is Are Harder:  [[?{Maths}]]** }}
```

### Twitch Chat (low viewership, I often copy/paste comments from twitch chat into roll20 for the players to see)

```roll20
&{template:atkdmg} {{desc=**Twitch Chat**
*?{Text?}*}}
```

### Generic Attack and Damage with Prompts for attack bonus and damage dice

```roll20
&{template:atkdmg} {{mod=Generic Attack}}  {{r1=[[ 1d20+?{Attack Mod|0} ]]}} {{always=1}} {{r2=[[1d20 +?{Attack Mod|0}]]}} {{attack=1}} {{damage=1}} {{dmg1flag=1}} {{dmg1=[[?{Damage Dice} + ?{Damage Mod} ]] }} {{dmg1type=dmg1type}} {{crit1=[[?{Damage Dice}]]}} 
```

### Generic d20 + prompt, with advantage/disadvantage

```roll20
&{template:simple}  {{mod=GM GENERIC ROLL}} {{r1=[[?{Dice?}]]}} {{always=1}} {{r2=[[?{Dice?}]]}}
```

### Generic Initiative Roll, prompting for initiative mod

```roll20
&{template:npc} 0 {{rname=Initiative}} {{mod=[[?{Initiative Modifier}]]}} {{r1=[[d20 + ?{Initiative Modifier} &{tracker}]]}} {{normal=1}} {{type=Initiative}}
```

### Healing Potions drop-down

```roll20
&{template:atkdmg}  {{damage=1}} {{dmg1flag=1}} ?{Healing Potion Variety?| Standard (2d4+2), {{rname=Standard Healing Potion 
(2d4+2)&#125;&#125;  {{dmg1=[[2d4+2]]&#125;&#125; |Greater (4d4+4), {{rname=Greater Healing Potion 
(4d4+4)&#125;&#125;  {{dmg1=[[4d4+4]]&#125;&#125; | Superior (8d4+8), {{rname=Superior Healing Potion 
(8d4+8)&#125;&#125;  {{dmg1=[[8d4+8]]&#125;&#125; |Supreme (10d4+20),{{rname=Supreme Healing Potion 
(10d4+20)&#125;&#125;  {{dmg1=[[10d4+20]]&#125;&#125; }
```

### Animated Object Attack Rolls drop-down

```roll20
&{template:atkdmg} {{mod=Animate Object Attack}} {{always=1}} {{attack=1}} {{damage=1}} {{dmg1flag=1}} ?{Animated Size:
|TINY, {{dmg1type=Tiny Bludgeoning &#125;&#125; {{r1=[[ 1d20+8]] &#125;&#125; {{r2=[[1d20+8]] &#125;&#125; {{dmg1=[[1d4+4]] &#125;&#125; {{crit1=[[1d4+4]]
|SMALL, {{dmg1type=Small Bludgeoning &#125;&#125; {{r1=[[ 1d20+6]] &#125;&#125; {{r2=[[1d20+6]] &#125;&#125; {{dmg1=[[1d8+2]] &#125;&#125; {{crit1=[[1d8+2]]
|MEDIUM, {{dmg1type=Medium Bludgeoning &#125;&#125; {{r1=[[ 1d20+5]] &#125;&#125; {{r2=[[1d20+5]] &#125;&#125; {{dmg1=[[2d6+1]] &#125;&#125; {{crit1=[[2d6+1]]
|LARGE, {{dmg1type=Large Bludgeoning &#125;&#125; {{r1=[[ 1d20+6]] &#125;&#125; {{r2=[[1d20+6]] &#125;&#125; {{dmg1=[[2d10+2]] &#125;&#125; {{crit1=[[2d10+2]]
|HUGE, {{dmg1type=Huge Bludgeoning &#125;&#125; {{r1=[[ 1d20+8]] &#125;&#125; {{r2=[[1d20+8]] &#125;&#125; {{dmg1=[[2d12+4]] &#125;&#125; {{crit1=[[2d12+4]] } }} 
```

### Sorcerer Metamagic Drop-Down

```roll20
@{wtype}&{template:atkdmg} {{desc=**Sorcerer MetaMagic**
Sorcerer Points Used: ?{MetaMagic Type
| Careful Spell(1), [[1]]
Select up to [[@{charisma_mod}]] targets to auto-succeed their save
| Distant(1), [[1]]
Touch Range becomes 30'
Ranges of 5' or greater are doubled
| Empowered(1), [[1]]
Reroll up to [[@{charisma_mod}]] damage dice
(Can be combined with other MetaMagic)
| Extended(1), [[1]]
Spell Durations of 1 min or more are doubled
| Heightend(3), [[3]]
Impose Disadvantage on target's first Save against effect
| Quickened(2), [[2]]
Casting time of 1 Action becomes Bonus Action (Mix a Bonus Action spell with a regular Cantrip. Not two regular spells)
| Subtle(1), [[1]]
Cast without Verbal or Somatic Components
| Twinned(Varies), **(SpellLevel)**

When target is one creature (not self) spend points equal to the spell level to target a second creature
} }}
```

## Additional contributions (Shemetz)

### Roll initiative for selected token (very simple)

```roll20
%{selected|initiative}
```

### Ability Check, Saving Throw, Skill Roll

And these three macros are very similar to each other: Ability Check, Saving Throw and Skill Roll. Each of them will prompt the user for which ability/skill to use and whether or not they have advantage/disadvantage, and then roll the result. If you want you can edit it to always roll advantage or to depend on default setting.

#### Ability Check

```roll20
@{selected|wtype}&{template:simple} {{name=Ability Score for @{selected|character_name}}} ?{Ability Score
  | Strength,        {{rname=Strength&#125;&#125;      {{mod=[[@{selected|strength_mod}]]&#125;&#125;       {{r1=[[@{selected|d20}+@{selected|strength_mod}       @{selected|jack_bonus}]]  &#125;&#125;{{r2=[[@{selected|d20}+@{selected|strength_mod}         @{selected|jack_bonus}]]      &#125;&#125;    {{?{Type of Roll&#124;Normal&#44;normal=1&#124;Advantage&#44;advantage=1&#124;Disadvantage&#44;disadvantage=1&#125; &#125;&#125;
  | Dexterity,       {{rname=Dexterity&#125;&#125;     {{mod=[[@{selected|dexterity_mod}]]&#125;&#125;      {{r1=[[@{selected|d20}+@{selected|dexterity_mod}      @{selected|jack_bonus}]]  &#125;&#125;{{r2=[[@{selected|d20}+@{selected|dexterity_mod}        @{selected|jack_bonus}]]      &#125;&#125;    {{?{Type of Roll&#124;Normal&#44;normal=1&#124;Advantage&#44;advantage=1&#124;Disadvantage&#44;disadvantage=1&#125; &#125;&#125;
  | Constitution,    {{rname=Constitution&#125;&#125;  {{mod=[[@{selected|constitution_mod}]]&#125;&#125;   {{r1=[[@{selected|d20}+@{selected|constitution_mod}   @{selected|jack_bonus}]]  &#125;&#125;{{r2=[[@{selected|d20}+@{selected|constitution_mod}     @{selected|jack_bonus}]]      &#125;&#125;    {{?{Type of Roll&#124;Normal&#44;normal=1&#124;Advantage&#44;advantage=1&#124;Disadvantage&#44;disadvantage=1&#125; &#125;&#125;
  | Intelligence,    {{rname=Intelligence&#125;&#125;  {{mod=[[@{selected|intelligence_mod}]]&#125;&#125;   {{r1=[[@{selected|d20}+@{selected|intelligence_mod}   @{selected|jack_bonus}]]  &#125;&#125;{{r2=[[@{selected|d20}+@{selected|intelligence_mod}     @{selected|jack_bonus}]]      &#125;&#125;    {{?{Type of Roll&#124;Normal&#44;normal=1&#124;Advantage&#44;advantage=1&#124;Disadvantage&#44;disadvantage=1&#125; &#125;&#125;
  | Wisdom,          {{rname=Wisdom&#125;&#125;        {{mod=[[@{selected|wisdom_mod}]]&#125;&#125;         {{r1=[[@{selected|d20}+@{selected|wisdom_mod}         @{selected|jack_bonus}]]  &#125;&#125;{{r2=[[@{selected|d20}+@{selected|wisdom_mod}           @{selected|jack_bonus}]]      &#125;&#125;    {{?{Type of Roll&#124;Normal&#44;normal=1&#124;Advantage&#44;advantage=1&#124;Disadvantage&#44;disadvantage=1&#125; &#125;&#125;
  | Charisma,        {{rname=Charisma&#125;&#125;      {{mod=[[@{selected|charisma_mod}]]&#125;&#125;       {{r1=[[@{selected|d20}+@{selected|charisma_mod}       @{selected|jack_bonus}]]  &#125;&#125;{{r2=[[@{selected|d20}+@{selected|charisma_mod}         @{selected|jack_bonus}]]      &#125;&#125;    {{?{Type of Roll&#124;Normal&#44;normal=1&#124;Advantage&#44;advantage=1&#124;Disadvantage&#44;disadvantage=1&#125; &#125;&#125;
}
```

#### Saving Throw

```roll20
@{selected|wtype}&{template:simple} {{name=Saving Throw for @{selected|character_name}}} ?{Saving Throw
  | Strength,        {{rname=Strength Save&#125;&#125;       {{r1=[[@{selected|d20}+[[(@{selected|strength_save_bonus}      @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_str_save}*@{selected|npc})]]]]&#125;&#125; {{r2=[[@{selected|d20}+[[(@{selected|strength_save_bonus}      @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_str_save}*@{selected|npc})]]]]&#125;&#125;    {{?{Type of Roll&#124;Normal&#44;normal=1&#124;Advantage&#44;advantage=1&#124;Disadvantage&#44;disadvantage=1&#125; &#125;&#125;
  | Dexterity,       {{rname=Dexterity Save&#125;&#125;      {{r1=[[@{selected|d20}+[[(@{selected|dexterity_save_bonus}     @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_dex_save}*@{selected|npc})]]]]&#125;&#125; {{r2=[[@{selected|d20}+[[(@{selected|dexterity_save_bonus}     @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_dex_save}*@{selected|npc})]]]]&#125;&#125;    {{?{Type of Roll&#124;Normal&#44;normal=1&#124;Advantage&#44;advantage=1&#124;Disadvantage&#44;disadvantage=1&#125; &#125;&#125;
  | Constitution,    {{rname=Constitution Save&#125;&#125;   {{r1=[[@{selected|d20}+[[(@{selected|constitution_save_bonus}  @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_con_save}*@{selected|npc})]]]]&#125;&#125; {{r2=[[@{selected|d20}+[[(@{selected|constitution_save_bonus}  @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_con_save}*@{selected|npc})]]]]&#125;&#125;    {{?{Type of Roll&#124;Normal&#44;normal=1&#124;Advantage&#44;advantage=1&#124;Disadvantage&#44;disadvantage=1&#125; &#125;&#125;
  | Intelligence,    {{rname=Intelligence Save&#125;&#125;   {{r1=[[@{selected|d20}+[[(@{selected|intelligence_save_bonus}  @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_int_save}*@{selected|npc})]]]]&#125;&#125; {{r2=[[@{selected|d20}+[[(@{selected|intelligence_save_bonus}  @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_int_save}*@{selected|npc})]]]]&#125;&#125;    {{?{Type of Roll&#124;Normal&#44;normal=1&#124;Advantage&#44;advantage=1&#124;Disadvantage&#44;disadvantage=1&#125; &#125;&#125;
  | Wisdom,          {{rname=Wisdom Save&#125;&#125;         {{r1=[[@{selected|d20}+[[(@{selected|wisdom_save_bonus}        @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_wis_save}*@{selected|npc})]]]]&#125;&#125; {{r2=[[@{selected|d20}+[[(@{selected|wisdom_save_bonus}        @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_wis_save}*@{selected|npc})]]]]&#125;&#125;    {{?{Type of Roll&#124;Normal&#44;normal=1&#124;Advantage&#44;advantage=1&#124;Disadvantage&#44;disadvantage=1&#125; &#125;&#125;
  | Charisma,        {{rname=Charisma Save&#125;&#125;       {{r1=[[@{selected|d20}+[[(@{selected|charisma_save_bonus}      @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_cha_save}*@{selected|npc})]]]]&#125;&#125; {{r2=[[@{selected|d20}+[[(@{selected|charisma_save_bonus}      @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_cha_save}*@{selected|npc})]]]]&#125;&#125;    {{?{Type of Roll&#124;Normal&#44;normal=1&#124;Advantage&#44;advantage=1&#124;Disadvantage&#44;disadvantage=1&#125; &#125;&#125;
}
```

#### Skill Roll

```roll20
@{selected|wtype}&{template:simple} {{name=Skill Check}} ?{Skill
  | Acrobatics,         {{rname=️Acrobatics&#125;&#125;        {{r1=[[@{selected|d20}+[[(@{selected|acrobatics_bonus}        @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_acrobatics}        *@{selected|npc})]]]]&#125;&#125;                                   {{r2=[[@{selected|d20}+[[(@{selected|acrobatics_bonus}           @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_acrobatics}        *@{selected|npc})]]]]&#125;&#125;   {{?{Type of Roll&#124;Normal&#44;normal=1&#124;Advantage&#44;advantage=1&#124;Disadvantage&#44;disadvantage=1&#125; &#125;&#125;
  | Animal Handling,    {{rname=Animal Handling&#125;&#125;   {{r1=[[@{selected|d20}+[[(@{selected|animal_handling_bonus}   @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_animal_handling}   *@{selected|npc})]]]]&#125;&#125;                                   {{r2=[[@{selected|d20}+[[(@{selected|animal_handling_bonus}      @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_animal_handling}   *@{selected|npc})]]]]&#125;&#125;   {{?{Type of Roll&#124;Normal&#44;normal=1&#124;Advantage&#44;advantage=1&#124;Disadvantage&#44;disadvantage=1&#125; &#125;&#125;
  | Arcana,             {{rname=Arcana&#125;&#125;            {{r1=[[@{selected|d20}+[[(@{selected|arcana_bonus}            @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_arcana}            *@{selected|npc})]]]]&#125;&#125;                                   {{r2=[[@{selected|d20}+[[(@{selected|arcana_bonus}               @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_arcana}            *@{selected|npc})]]]]&#125;&#125;   {{?{Type of Roll&#124;Normal&#44;normal=1&#124;Advantage&#44;advantage=1&#124;Disadvantage&#44;disadvantage=1&#125; &#125;&#125;
  | Athletics,          {{rname=️Athletics&#125;&#125;         {{r1=[[@{selected|d20}+[[(@{selected|athletics_bonus}         @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_athletics}         *@{selected|npc})]]]]&#125;&#125;                                   {{r2=[[@{selected|d20}+[[(@{selected|athletics_bonus}            @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_athletics}         *@{selected|npc})]]]]&#125;&#125;   {{?{Type of Roll&#124;Normal&#44;normal=1&#124;Advantage&#44;advantage=1&#124;Disadvantage&#44;disadvantage=1&#125; &#125;&#125;
  | Deception,          {{rname=Deception&#125;&#125;         {{r1=[[@{selected|d20}+[[(@{selected|deception_bonus}         @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_deception}         *@{selected|npc})]]]]&#125;&#125;                                   {{r2=[[@{selected|d20}+[[(@{selected|deception_bonus}            @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_deception}         *@{selected|npc})]]]]&#125;&#125;   {{?{Type of Roll&#124;Normal&#44;normal=1&#124;Advantage&#44;advantage=1&#124;Disadvantage&#44;disadvantage=1&#125; &#125;&#125;
  | History,            {{rname=History&#125;&#125;           {{r1=[[@{selected|d20}+[[(@{selected|history_bonus}           @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_history}           *@{selected|npc})]]]]&#125;&#125;                                   {{r2=[[@{selected|d20}+[[(@{selected|history_bonus}              @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_history}           *@{selected|npc})]]]]&#125;&#125;   {{?{Type of Roll&#124;Normal&#44;normal=1&#124;Advantage&#44;advantage=1&#124;Disadvantage&#44;disadvantage=1&#125; &#125;&#125;
  | Insight,            {{rname=Insight&#125;&#125;           {{r1=[[@{selected|d20}+[[(@{selected|insight_bonus}           @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_insight}           *@{selected|npc})]]]]&#125;&#125;                                   {{r2=[[@{selected|d20}+[[(@{selected|insight_bonus}              @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_insight}           *@{selected|npc})]]]]&#125;&#125;   {{?{Type of Roll&#124;Normal&#44;normal=1&#124;Advantage&#44;advantage=1&#124;Disadvantage&#44;disadvantage=1&#125; &#125;&#125;
  | Intimidation,       {{rname=Intimidation&#125;&#125;      {{r1=[[@{selected|d20}+[[(@{selected|intimidation_bonus}      @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_intimidation}      *@{selected|npc})]]]]&#125;&#125;                                   {{r2=[[@{selected|d20}+[[(@{selected|intimidation_bonus}         @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_intimidation}      *@{selected|npc})]]]]&#125;&#125;   {{?{Type of Roll&#124;Normal&#44;normal=1&#124;Advantage&#44;advantage=1&#124;Disadvantage&#44;disadvantage=1&#125; &#125;&#125;
  | Investigation,      {{rname=‍️Investigation&#125;&#125;     {{r1=[[@{selected|d20}+[[(@{selected|investigation_bonus}     @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_investigation}     *@{selected|npc})]]]]&#125;&#125;                                   {{r2=[[@{selected|d20}+[[(@{selected|investigation_bonus}        @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_investigation}     *@{selected|npc})]]]]&#125;&#125;   {{?{Type of Roll&#124;Normal&#44;normal=1&#124;Advantage&#44;advantage=1&#124;Disadvantage&#44;disadvantage=1&#125; &#125;&#125;
  | Medicine,           {{rname=Medicine&#125;&#125;          {{r1=[[@{selected|d20}+[[(@{selected|medicine_bonus}          @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_medicine}          *@{selected|npc})]]]]&#125;&#125;                                   {{r2=[[@{selected|d20}+[[(@{selected|medicine_bonus}             @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_medicine}          *@{selected|npc})]]]]&#125;&#125;   {{?{Type of Roll&#124;Normal&#44;normal=1&#124;Advantage&#44;advantage=1&#124;Disadvantage&#44;disadvantage=1&#125; &#125;&#125;
  | Nature,             {{rname=Nature&#125;&#125;            {{r1=[[@{selected|d20}+[[(@{selected|nature_bonus}            @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_nature}            *@{selected|npc})]]]]&#125;&#125;                                   {{r2=[[@{selected|d20}+[[(@{selected|nature_bonus}               @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_nature}            *@{selected|npc})]]]]&#125;&#125;   {{?{Type of Roll&#124;Normal&#44;normal=1&#124;Advantage&#44;advantage=1&#124;Disadvantage&#44;disadvantage=1&#125; &#125;&#125;
  | Perception,         {{rname=Perception&#125;&#125;        {{r1=[[@{selected|d20}+[[(@{selected|perception_bonus}        @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_perception}        *@{selected|npc})]]]]&#125;&#125;                                   {{r2=[[@{selected|d20}+[[(@{selected|perception_bonus}           @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_perception}        *@{selected|npc})]]]]&#125;&#125;   {{?{Type of Roll&#124;Normal&#44;normal=1&#124;Advantage&#44;advantage=1&#124;Disadvantage&#44;disadvantage=1&#125; &#125;&#125;
  | Performance,        {{rname=Performance&#125;&#125;       {{r1=[[@{selected|d20}+[[(@{selected|performance_bonus}       @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_performance}       *@{selected|npc})]]]]&#125;&#125;                                   {{r2=[[@{selected|d20}+[[(@{selected|performance_bonus}          @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_performance}       *@{selected|npc})]]]]&#125;&#125;   {{?{Type of Roll&#124;Normal&#44;normal=1&#124;Advantage&#44;advantage=1&#124;Disadvantage&#44;disadvantage=1&#125; &#125;&#125;
  | Persuasion,         {{rname=Persuasion&#125;&#125;        {{r1=[[@{selected|d20}+[[(@{selected|persuasion_bonus}        @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_persuasion}        *@{selected|npc})]]]]&#125;&#125;                                   {{r2=[[@{selected|d20}+[[(@{selected|persuasion_bonus}           @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_persuasion}        *@{selected|npc})]]]]&#125;&#125;   {{?{Type of Roll&#124;Normal&#44;normal=1&#124;Advantage&#44;advantage=1&#124;Disadvantage&#44;disadvantage=1&#125; &#125;&#125;
  | Religion,           {{rname=Religion&#125;&#125;          {{r1=[[@{selected|d20}+[[(@{selected|religion_bonus}          @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_religion}          *@{selected|npc})]]]]&#125;&#125;                                   {{r2=[[@{selected|d20}+[[(@{selected|religion_bonus}             @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_religion}          *@{selected|npc})]]]]&#125;&#125;   {{?{Type of Roll&#124;Normal&#44;normal=1&#124;Advantage&#44;advantage=1&#124;Disadvantage&#44;disadvantage=1&#125; &#125;&#125;
  | Sleight of Hand,    {{rname=Sleight of Hand&#125;&#125;   {{r1=[[@{selected|d20}+[[(@{selected|sleight_of_hand_bonus}   @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_sleight_of_hand}   *@{selected|npc})]]]]&#125;&#125;                                   {{r2=[[@{selected|d20}+[[(@{selected|sleight_of_hand_bonus}      @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_sleight_of_hand}   *@{selected|npc})]]]]&#125;&#125;   {{?{Type of Roll&#124;Normal&#44;normal=1&#124;Advantage&#44;advantage=1&#124;Disadvantage&#44;disadvantage=1&#125; &#125;&#125;
  | Stealth,            {{rname=Stealth&#125;&#125;           {{r1=[[@{selected|d20}+[[(@{selected|stealth_bonus}           @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_stealth}           *@{selected|npc})]]]]&#125;&#125;                                   {{r2=[[@{selected|d20}+[[(@{selected|stealth_bonus}              @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_stealth}           *@{selected|npc})]]]]&#125;&#125;   {{?{Type of Roll&#124;Normal&#44;normal=1&#124;Advantage&#44;advantage=1&#124;Disadvantage&#44;disadvantage=1&#125; &#125;&#125;
  | Survival,           {{rname=Survival&#125;&#125;          {{r1=[[@{selected|d20}+[[(@{selected|survival_bonus}          @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_survival}          *@{selected|npc})]]]]&#125;&#125;                                   {{r2=[[@{selected|d20}+[[(@{selected|survival_bonus}             @{selected|pbd_safe}*(1-ceil((@{selected|npc})*0.1)))+(@{selected|npc_survival}          *@{selected|npc})]]]]&#125;&#125;   {{?{Type of Roll&#124;Normal&#44;normal=1&#124;Advantage&#44;advantage=1&#124;Disadvantage&#44;disadvantage=1&#125; &#125;&#125;
}
```

## Additional contribution (LeoncinoSpillato)

[[D&D 5e from Roll20 sheet] [No API] Token Action - Players/DM Master Query Macro for Rolls: Attributes, Saving Throws, Ability Checks!](https://www.reddit.com/r/Roll20/comments/rbep4h/dd_5e_from_roll20_sheet_no_api_token_action/)

```roll20
@{selected|wtype} &{template:simple} {{always=1}} ?{Roll|

-🧬ABILITIES-|

[@{selected|strength_mod}] 💪Strength, {{rname= 💪Strength Roll&#125;&#125; {{mod=[[ [[@{selected|strength_mod}]] [STR] ]]&#125;&#125; {{r1=[[ @{selected|d20} + [[@{selected|strength_mod}]] [STR] ]]&#125;&#125; {{r2=[[ @{selected|d20} + [[@{selected|strength_mod}]] [STR] ]]&#125;&#125; |

[@{selected|dexterity_mod}] 🎯Dexterity, {{rname= 🎯Dexterity Roll&#125;&#125; {{mod=[[ [[@{selected|dexterity_mod}]] [DEX] ]]&#125;&#125; {{r1=[[ @{selected|d20} + [[@{selected|dexterity_mod}]] [DEX] ]]&#125;&#125; {{r2=[[ @{selected|d20} + [[@{selected|dexterity_mod}]] [DEX] ]]&#125;&#125; |

[@{selected|constitution_mod}] 🧬Constitution, {{rname= 🧬Constitution Roll&#125;&#125; {{mod=[[ [[@{selected|constitution_mod}]] [CON] ]]&#125;&#125; {{r1=[[ @{selected|d20} + [[@{selected|constitution_mod}]] [CON] ]]&#125;&#125; {{r2=[[ @{selected|d20} + [[@{selected|constitution_mod}]] [CON] ]]&#125;&#125; |

[@{selected|intelligence_mod}] 🧠Intelligence, {{rname= 🧠Intelligence Roll&#125;&#125; {{mod=[[ [[@{selected|intelligence_mod}]] [INT] ]]&#125;&#125; {{r1=[[ @{selected|d20} + [[@{selected|intelligence_mod}]] [INT] ]]&#125;&#125; {{r2=[[ @{selected|d20} + [[@{selected|intelligence_mod}]] [INT] ]]&#125;&#125; |

[@{selected|wisdom_mod}] 🌌Wisdom, {{rname= 🌌Wisdom Roll&#125;&#125; {{mod=[[ [[@{selected|wisdom_mod}]] [WIS] ]]&#125;&#125; {{r1=[[ @{selected|d20} + [[@{selected|wisdom_mod}]] [WIS] ]]&#125;&#125; {{r2=[[ @{selected|d20} + [[@{selected|wisdom_mod}]] [WIS] ]]&#125;&#125; |

[@{selected|charisma_mod}] 🎭Charisma, {{rname=🎭Charisma Roll&#125;&#125; {{mod=[[ [[@{selected|charisma_mod}]] [CHA] ]]&#125;&#125; {{r1=[[ @{selected|d20} + [[@{selected|charisma_mod}]] [CHA] ]]&#125;&#125; {{r2=[[ @{selected|d20} + [[@{selected|charisma_mod}]] [CHA] ]]&#125;&#125; |

-----------------------------------|

-😨❗ SAVING THROWS-|

[@{selected|strength_save_bonus}] 😤Strength Saving Throw, {{rname=😤Strength Saving Throw&#125;&#125; {{mod=[[ @{selected|strength_save_bonus} ]]&#125;&#125; {{r1=[[ @{selected|d20} + [[@{selected|strength_save_prof}]][Proficiency] + @{selected|strength_mod}[Strength] ]]&#125;&#125; {{r2=[[ @{selected|d20} + [[@{selected|strength_save_prof}]][Proficiency] + @{selected|strength_mod}[Strength] ]]&#125;&#125; {{global=@{selected|global_save_mod}&#125;&#125; |

[@{selected|dexterity_save_bonus}] 💨Dexterity Saving Throw, {{rname=💨Dexterity Saving Throw&#125;&#125; {{mod=[[ @{selected|dexterity_save_bonus} ]]&#125;&#125; {{r1=[[ @{selected|d20} + [[@{selected|dexterity_save_prof}]][Proficiency] + @{selected|dexterity_mod}[Dexterity] ]]&#125;&#125; {{r2=[[ @{selected|d20} + [[@{selected|dexterity_save_prof}]][Proficiency] + @{selected|dexterity_mod}[Dexterity] ]]&#125;&#125; {{global=@{selected|global_save_mod}&#125;&#125; |

[@{selected|constitution_save_bonus}] 🤒Constitution Saving Throw, {{rname=🤒Constitution Saving Throw&#125;&#125; {{mod=[[ @{selected|constitution_save_bonus} ]]&#125;&#125; {{r1=[[ @{selected|d20} + [[@{selected|constitution_save_prof}]][Proficiency] + @{selected|constitution_mod}[Constitution] ]]&#125;&#125; {{r2=[[ @{selected|d20} + [[@{selected|constitution_save_prof}]][Proficiency] + @{selected|constitution_mod}[Constitution] ]]&#125;&#125; {{global=@{selected|global_save_mod}&#125;&#125; |

[@{selected|intelligence_save_bonus}] 🧐Intelligence Saving Throw, {{rname=🧐Intelligence Saving Throw&#125;&#125; {{mod=[[ @{selected|intelligence_save_bonus} ]]&#125;&#125; {{r1=[[ @{selected|d20} + [[@{selected|intelligence_save_prof}]][Proficiency] + @{selected|intelligence_mod}[Intelligence] ]]&#125;&#125; {{r2=[[ @{selected|d20} + [[@{selected|intelligence_save_prof}]][Proficiency] + @{selected|intelligence_mod}[Intelligence] ]]&#125;&#125; {{global=@{selected|global_save_mod}&#125;&#125; |

[@{selected|wisdom_save_bonus}] 😵Wisdom Saving Throw, {{rname=😵Wisdom Saving Throw&#125;&#125; {{mod=[[ @{selected|wisdom_save_bonus} ]]&#125;&#125; {{r1=[[ @{selected|d20} + [[@{selected|wisdom_save_prof}]][Proficiency] + @{selected|wisdom_mod}[Wisdom] ]]&#125;&#125; {{r2=[[ @{selected|d20} + [[@{selected|wisdom_save_prof}]][Proficiency] + @{selected|wisdom_mod}[Wisdom] ]]&#125;&#125; {{global=@{selected|global_save_mod}&#125;&#125; |

[@{selected|charisma_save_bonus}] 😎Charisma Saving Throw, {{rname=😎Charisma Saving Throw&#125;&#125; {{mod=[[ @{selected|charisma_save_bonus} ]]&#125;&#125; {{r1=[[ @{selected|d20} + [[@{selected|charisma_save_prof}]][Proficiency] + @{selected|charisma_mod}[Charisma] ]]&#125;&#125; {{r2=[[ @{selected|d20} + [[@{selected|charisma_save_prof}]][Proficiency] + @{selected|charisma_mod}[Charisma] ]]&#125;&#125; {{global=@{selected|global_save_mod}&#125;&#125; |

-----------------------------------|

-🛠️SKILLS-|

[@{selected|athletics_bonus}] (STR)💪Athletics, {{rname=💪Athletics&#125;&#125; {{mod=[[ [[@{selected|athletics_bonus}]] [ATL] ]]&#125;&#125; {{r1=[[ @{selected|d20} + [[@{selected|athletics_prof}]][Proficiency] + @{selected|strength_mod}[Strength]]]&#125;&#125; {{r2=[[ @{selected|d20} + [[@{selected|athletics_prof}]][Proficiency] + @{selected|strength_mod}[Strength]]]&#125;&#125; {{global=@{selected|global_skill_mod}&#125;&#125; |

[@{selected|acrobatics_bonus}] (DEX)🤸Acrobatics, {{rname=🤸Acrobatics&#125;&#125; {{mod=[[ [[@{selected|acrobatics_bonus}]] [ACROB] ]]&#125;&#125; {{r1=[[ @{selected|d20} + [[@{selected|acrobatics_prof}]][Proficiency] + @{selected|dexterity_mod}[Dexterity]]]&#125;&#125; {{r2=[[ @{selected|d20} + [[@{selected|acrobatics_prof}]][Proficiency] + @{selected|dexterity_mod}[Dexterity]]]&#125;&#125; {{global=@{selected|global_skill_mod}&#125;&#125; |

[@{selected|sleight_of_hand_bonus}] (DEX)🤏Sleight of Hand, {{rname=🤏Sleight of Hand&#125;&#125; {{mod=[[ [[@{selected|sleight_of_hand_bonus}]] [RAPID MANO] ]]&#125;&#125; {{r1=[[ @{selected|d20} + [[@{selected|sleight_of_hand_prof}]][Proficiency] + @{selected|dexterity_mod}[Dexterity]]]&#125;&#125; {{r2=[[ @{selected|d20} + [[@{selected|sleight_of_hand_prof}]][Proficiency] + @{selected|dexterity_mod}[Dexterity]]]&#125;&#125; {{global=@{selected|global_skill_mod}&#125;&#125; |

[@{selected|stealth_bonus}] (DEX)👤Stealth, {{rname=👤Stealth&#125;&#125; {{mod=[[ [[@{selected|stealth_bonus}]] [STEALTH] ]]&#125;&#125; {{r1=[[ @{selected|d20} + [[@{selected|stealth_prof}]][Proficiency] + @{selected|dexterity_mod}[Dexterity]]]&#125;&#125; {{r2=[[ @{selected|d20} + [[@{selected|stealth_prof}]][Proficiency] + @{selected|dexterity_mod}[Dexterity]]]&#125;&#125; {{global=@{selected|global_skill_mod}&#125;&#125; |

[@{selected|arcana_bonus}] (Int)🔯Arcana, {{rname=🔯Arcana&#125;&#125; {{mod=[[ [[@{selected|arcana_bonus}]] [ARC] ]]&#125;&#125; {{r1=[[ @{selected|d20} + [[@{selected|arcana_prof}]][Proficiency] + @{selected|intelligence_mod}[Intelligence]]]&#125;&#125; {{r2=[[ @{selected|d20} + [[@{selected|arcana_prof}]][Proficiency] + @{selected|intelligence_mod}[Intelligence]]]&#125;&#125; {{global=@{selected|global_skill_mod}&#125;&#125; |

[@{selected|history_bonus}] (Int)📖History, {{rname=📖History&#125;&#125; {{mod=[[ [[@{selected|history_bonus}]][STO] ]]&#125;&#125; {{r1=[[ @{selected|d20} + [[@{selected|history_prof}]][Proficiency] + @{selected|intelligence_mod}[Intelligence]]]&#125;&#125; {{r2=[[ @{selected|d20} + [[@{selected|history_prof}]][Proficiency] + @{selected|intelligence_mod}[Intelligence]]]&#125;&#125; {{global=@{selected|global_skill_mod}&#125;&#125; |

[@{selected|investigation_bonus}] (Int)🔍Investigation, {{rname=🔍Investigation&#125;&#125; {{mod=[[ [[@{selected|investigation_bonus}]] [IND] ]]&#125;&#125; {{r1=[[ @{selected|d20} + [[@{selected|investigation_prof}]][Proficiency] + @{selected|intelligence_mod}[Intelligence]]]&#125;&#125; {{r2=[[ @{selected|d20} + [[@{selected|investigation_prof}]][Proficiency] + @{selected|intelligence_mod}[Intelligence]]]&#125;&#125; {{global=@{selected|global_skill_mod}&#125;&#125; |

[@{selected|nature_bonus}] (Int)🌄Nature, {{rname=🌄Nature&#125;&#125; {{mod=[[ [[@{selected|nature_bonus}]] [NAT] ]]&#125;&#125; {{r1=[[ @{selected|d20} + [[@{selected|nature_prof}]][Proficiency] + @{selected|intelligence_mod}[Intelligence]]]&#125;&#125; {{r2=[[ @{selected|d20} + [[@{selected|nature_prof}]][Proficiency] + @{selected|intelligence_mod}[Intelligence]]]&#125;&#125; {{global=@{selected|global_skill_mod}&#125;&#125; |

[@{selected|religion_bonus}] (Int)🕎Religion, {{rname=🕎Religion&#125;&#125; {{mod=[[ [[@{selected|religion_bonus}]] [RELI] ]]&#125;&#125; {{r1=[[ @{selected|d20} + [[@{selected|religion_prof}]][Proficiency] + @{selected|intelligence_mod}[Intelligence]]]&#125;&#125; {{r2=[[ @{selected|d20} + [[@{selected|religion_prof}]][Proficiency] + @{selected|intelligence_mod}[Intelligence]]]&#125;&#125; {{global=@{selected|global_skill_mod}&#125;&#125; |

[@{selected|animal_handling_bonus}] (WIS)🐶Animal Handling, {{rname=🐶Animal Handling&#125;&#125; {{mod=[[ [[@{selected|animal_handling_bonus}]] [ADD ANIM] ]]&#125;&#125; {{r1=[[ @{selected|d20} + [[@{selected|animal_handling_prof}]][Proficiency] + @{selected|wisdom_mod}[Wisdom]]]&#125;&#125; {{r2=[[ @{selected|d20} + [[@{selected|animal_handling_prof}]][Proficiency] + @{selected|wisdom_mod}[Wisdom]]]&#125;&#125; {{global=@{selected|global_skill_mod}&#125;&#125; |

[@{selected|insight_bonus}] (WIS)🤔Insight, {{rname=🤔Insight&#125;&#125; {{mod=[[ [[@{selected|insight_bonus}]] [INTU] ]]&#125;&#125; {{r1=[[ @{selected|d20} + [[@{selected|insight_prof}]][Proficiency] + @{selected|wisdom_mod}[Wisdom]]]&#125;&#125; {{r2=[[ @{selected|d20} + [[@{selected|insight_prof}]][Proficiency] + @{selected|wisdom_mod}[Wisdom]]]&#125;&#125; {{global=@{selected|global_skill_mod}&#125;&#125; |

[@{selected|medicine_bonus}] (WIS)🩺Medicine, {{rname=🩺Medicine&#125;&#125; {{mod=[[ [[@{selected|medicine_bonus}]] [MED] ]]&#125;&#125; {{r1=[[ @{selected|d20} + [[@{selected|medicine_prof}]][Proficiency] + @{selected|wisdom_mod}[Wisdom]]]&#125;&#125; {{r2=[[ @{selected|d20} + [[@{selected|medicine_prof}]][Proficiency] + @{selected|wisdom_mod}[Wisdom]]]&#125;&#125; {{global=@{selected|global_skill_mod}&#125;&#125; |

[@{selected|perception_bonus}] (WIS)👀Perception, {{rname=👀Perception&#125;&#125; {{mod=[[ [[@{selected|perception_bonus}]] [PERC] ]]&#125;&#125; {{r1=[[ @{selected|d20} + [[@{selected|perception_prof}]][Proficiency] + @{selected|wisdom_mod}[Wisdom]]]&#125;&#125; {{r2=[[ @{selected|d20} + [[@{selected|perception_prof}]][Proficiency] + @{selected|wisdom_mod}[Wisdom]]]&#125;&#125; {{global=@{selected|global_skill_mod}&#125;&#125; |

[@{selected|survival_bonus}] (WIS)🐾Survival, {{rname=🐾Survival&#125;&#125; {{mod=[[ [[@{selected|survival_bonus}]] [SOPRAV] ]]&#125;&#125; {{r1=[[ @{selected|d20} + [[@{selected|survival_prof}]][Proficiency] + @{selected|wisdom_mod}[Wisdom]]]&#125;&#125; {{r2=[[ @{selected|d20} + [[@{selected|survival_prof}]][Proficiency] + @{selected|wisdom_mod}[Wisdom]]]&#125;&#125; {{global=@{selected|global_skill_mod}&#125;&#125; |

[@{selected|deception_bonus}] (CHA)🤞Deception, {{rname=🤞Deception&#125;&#125; {{mod=[[ [[@{selected|deception_bonus}]] [INGAN] ]]&#125;&#125; {{r1=[[ @{selected|d20} + [[@{selected|deception_prof}]][Proficiency] + @{selected|charisma_mod}[Charisma]]]&#125;&#125; {{r2=[[ @{selected|d20} + [[@{selected|deception_prof}]][Proficiency] + @{selected|charisma_mod}[Charisma]]]&#125;&#125; {{global=@{selected|global_skill_mod}&#125;&#125; |

[@{selected|intimidation_bonus}] (CHA)👹Intimidation, {{rname=👹Intimidation&#125;&#125; {{mod=[[ [[@{selected|intimidation_bonus}]] [INTIM] ]]&#125;&#125; {{r1=[[ @{selected|d20} + [[@{selected|intimidation_prof}]][Proficiency] + @{selected|charisma_mod}[Charisma]]]&#125;&#125; {{r2=[[ @{selected|d20} + [[@{selected|intimidation_prof}]][Proficiency] + @{selected|charisma_mod}[Charisma]]]&#125;&#125; {{global=@{selected|global_skill_mod}&#125;&#125; |

[@{selected|performance_bonus}] (CHA)🤹Performance, {{rname=🤹Performance&#125;&#125; {{mod=[[ [[@{selected|performance_bonus}]] [PERF] ]]&#125;&#125; {{r1=[[ @{selected|d20} + [[@{selected|performance_prof}]][Proficiency] + @{selected|charisma_mod}[Charisma]]]&#125;&#125; {{r2=[[ @{selected|d20} + [[@{selected|performance_prof}]][Proficiency] + @{selected|charisma_mod}[Charisma]]]&#125;&#125; {{global=@{selected|global_skill_mod}&#125;&#125; |

[@{selected|persuasion_bonus}] (CHA)🤝Persuasion, {{rname=🤝Persuasion&#125;&#125; {{mod=[[ [[@{selected|persuasion_bonus}]] [PERS] ]]&#125;&#125; {{r1=[[ @{selected|d20} + [[@{selected|persuasion_prof}]][Proficiency] + @{selected|charisma_mod}[Charisma]]]&#125;&#125; {{r2=[[ @{selected|d20} + [[@{selected|persuasion_prof}]][Proficiency] + @{selected|charisma_mod}[Charisma]]]&#125;&#125; {{global=@{selected|global_skill_mod}&#125;&#125;

} @{selected|charname_output}&{noerror}
```
# Celeste macros

## Aurelie attack with optional opportunity attack text

```roll20
&{template:default} {{?{Attack style|Normal,Attack Action=Celeste lashes out with Aurelie|Opportunity,Opportunity Attack (Reaction)=Celeste thrusts Aurelie at the space invader}}}
%{Celeste Anaej Brakride|repeating_attack_-MdCv-xjHLYjkkLb8AdV_attack}
%{Celeste Anaej Brakride|Divine-Strike.} {{desc=[**On a succesful hit** add Divine Strike](#" style="color:#7e2d40;font-size:18px;display:block:text-align:center;margin-bottom:5px)}}
```

## Aurelie bonus polearm attack

```roll20
&{template:default} {{Bonus Action=Celeste brings Aurelie about for a follow-up}}
%{Celeste Anaej Brakride|repeating_attack_-MfWu-39jR0K9gTRvuSc_attack}
```

## Spiritual Weapon with only even number spell slot selection

```roll20
?{Cast at what level?|Level 2,0|Level 4,2|Level 6,4|Level 8,6}
%{Celeste Anaej Brakride|repeating_attack_-Mc4snRrDjgG03mVl0gs_attack}
```

## Divine Strike

```roll20
&{template:dmg} {{rname=Divine Strike}} {{range}} {{damage=1}} {{dmg1flag=1}} {{dmg1=[[2d8]]}} {{dmg1type=Radiant}} {{dmg2flag}} {{crit}} {{save}} {{saveattr}} {{savedesc}} {{savedc}} {{desc}} {{hldmg}} {{spelllevel}} ammo @{Celeste Anaej Brakride|charname_output}
```

## Perception with Brinewall Shield

```roll20
&{template:traits} {{name=Brinewall Shield sight}} {{source=Item:Brinewall Shield}} {{description=You have advantage on initiative rolls and Wisdom (Perception) checks. The shield is emblazoned with a image of Castle Brinewall. The crescent arc of the sun over the castle is shaped in the symbol of an eye.}}
@{Celeste Anaej Brakride|wtype}&{template:simple} {{rname=^{perception}}} {{advantage=1}} {{mod=@{Celeste Anaej Brakride|perception_bonus}}} {{r1=[[@{Celeste Anaej Brakride|d20}+@{Celeste Anaej Brakride|pb}[Proficiency]+@{Celeste Anaej Brakride|wisdom_mod}[Wisdom]@{Celeste Anaej Brakride|pbd_safe}]]}} {{r2=[[@{Celeste Anaej Brakride|d20}+@{Celeste Anaej Brakride|pb}[Proficiency]+@{Celeste Anaej Brakride|wisdom_mod}[Wisdom]@{Celeste Anaej Brakride|pbd_safe}]]}} {{global=@{Celeste Anaej Brakride|global_skill_mod}}} @{Celeste Anaej Brakride|charname_output}
```

## Stealth check with optional Pass Without Trace

```roll20
@{wtype}&{template:simple} {{rname=^{stealth-u}}} {{mod=@{stealth_bonus}}} {{r1=[[@{d20}+@{stealth_bonus}[Mods]@{pbd_safe}?{Pass Without Trace|Inactive|Active,+10[Pass Without Trace]}]]}} {{query=1}} ?{Advantage?|Normal Roll,&#123&#123normal=1&#125&#125 &#123&#123r2=[[0d20|Advantage,&#123&#123advantage=1&#125&#125 &#123&#123r2=[[@{d20}|Disadvantage,&#123&#123disadvantage=1&#125&#125 &#123&#123r2=[[@{d20}}+@{stealth_bonus}[Mods]@{pbd_safe}?{Pass Without Trace|Inactive|Active,+10[Pass Without Trace]}]]}} {{global=@{global_skill_mod}}} @{charname_output}
[img](https://i.pinimg.com/originals/16/45/a8/1645a8c741430a7e484583f88809d4f0.gif)
```

## Radiant Soul (Protector Aasimar)

```roll20
&{template:spell} {{name=Radiant Soul}} {{level=@{{level}}}} {{castingtime=1 action}} {{target=self}} {{s=1}} {{duration=1 minute}} {{description=Starting at 3rd level, you can use your action to unleash the divine energy within yourself, causing your eyes to glimmer and two luminous, incorporeal wings to sprout from your back.

Your transformation lasts for 1 minute or until you end it as a bonus action. During it, you have a flying speed of 30 feet, and once on each of your turns, you can deal extra radiant damage to one target when you deal damage to it with an attack or a spell. The extra radiant damage equals your level.}} {{charname=Celeste}}

!setattr --charid -M_uD0cDh9DH2BP2efp7 --silent --repeating_damagemod_-MiH4iKdZ9LOJsXgVLjm_global_damage_active_flag|1
```

```roll20
!setattr --charid -M_uD0cDh9DH2BP2efp7 --silent --repeating_damagemod_-MiH4iKdZ9LOJsXgVLjm_global_damage_active_flag|0
```
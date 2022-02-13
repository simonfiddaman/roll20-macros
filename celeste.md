# Celeste macros

## Aurelie attack with optional opportunity attack text

```roll20
&{template:default} {{?{Attack style|Normal,Attack Action=Celeste lashes out with Aurelie|Opportunity,Opportunity Attack (Reaction)=Celeste thrusts Aurelie at the space invader}}}
%{Celeste Anaej Brakride|repeating_attack_$0_attack}
%{Celeste Anaej Brakride|Divine-Strike} {{desc=[**On a succesful hit** add Divine Strike](#" style="color:#7e2d40;font-size:18px;display:block:text-align:center;margin-bottom:5px)}}
```

## Aurelie bonus polearm attack

```roll20
&{template:default} {{Bonus Action=Celeste brings Aurelie about for a follow-up}}
%{Celeste Anaej Brakride|repeating_attack_$2_attack}
```

## Spiritual Weapon with only even number spell slot selection

```roll20
?{Cast at what level?|Level 2,0|Level 4,1|Level 6,2|Level 8,3}
%{Celeste Anaej Brakride|repeating_attack_$2_attack}
```

## Divine Strike

```roll20
&{template:dmg} {{rname=Divine Strike}} {{range}} {{damage=1}} {{dmg1flag=1}} {{dmg1=[[1d8]]}} {{dmg1type=Radiant}} {{dmg2flag}} {{crit}} {{save}} {{saveattr}} {{savedesc}} {{savedc}} {{desc}} {{hldmg}} {{spelllevel}} ammo @{Celeste Anaej Brakride|charname_output}
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

# Healing potions (our game)

```roll20
&{template:atkdmg}  {{damage=1}} {{dmg1flag=1}} ?{Healing Potion Variety?
|Cure Light Wounds (1d8+4), {{rname=Cure Light Wounds Potion (1d8+4)&#125;&#125;  {{dmg1=[[1d8+4[Healing]]]&#125;&#125;  {{dmg1type=Healing&#125;&#125;
|Cure Moderate Wounds (2d8+5), {{rname=Cure Moderate Wounds Potion (2d8+5)&#125;&#125;  {{dmg1=[[2d8+5[Healing]]]&#125;&#125;  {{dmg1type=Healing&#125;&#125;
|Cure Serious Wounds (3d8+7), {{rname=Cure Serious Wounds Potion (3d8+7)&#125;&#125;  {{dmg1=[[3d8+7[Healing]]]&#125;&#125;  {{dmg1type=Healing&#125;&#125;
|Cure Critical Wounds (4d8+9), {{rname=Cure Critical Wounds Potion (4d4+9)&#125;&#125;  {{dmg1=[[4d8+9[Healing]]]&#125;&#125;  {{dmg1type=Healing&#125;&#125;
}
```
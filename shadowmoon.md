# Shadow Moon macros

## Suishen reference attack

```roll20
@{Shadow Moon|wtype}&{template:atkdmg} {{mod=+17}} {{rname=(AD) Suishen +5}} {{r1=[[@{Shadow Moon|d20}cs>20 + 8[DEX] + 5[PROF] + 5[MAGIC]]]}} @{Shadow Moon|rtype}cs>20 + 8[DEX] + 5[PROF] + 5[MAGIC]]]}} {{attack=1}} {{range=}} {{damage=1}} {{dmg1flag=1}} {{dmg1=[[1d8 + 8[DEX] + 5[MAGIC]]]}} {{dmg1type=Slashing}} {{damage=1}} {{dmg2flag=1}} {{dmg2=[[1d6]]}} {{dmg2type=Fire}} {{crit1=[[1d8[CRIT]]]}} {{crit2=[[1d6[CRIT]]]}} 0 {{desc=}}   {{spelllevel=}} {{innate=}} {{globalattack=@{Shadow Moon|global_attack_mod}}} {{globaldamage=[[0]]}} {{globaldamagecrit=[[0]]}} {{globaldamagetype=@{Shadow Moon|global_damage_mod_type}}} ammo= @{Shadow Moon|charname_output}
```

## Suishen double attack (attacking) with scabbard of vigor

```roll20
@{selected|wtype}&{template:default} {{Suishen Attacking=?{Scabbard of Vigor|Not Active,+0[Scabbard of Vigor not used]|+4 for 1 round,+4[Scabbard of Vigor for 1 round]|+3 for 3 rounds,+3[Scabbard of Vigor for 3 rounds]|+2 for 5 rounds,+2[Scabbard of Vigor for 5 rounds]|+1 for 10 rounds,+1[Scabbard of Vigor for 10 rounds]}}}
@{selected|wtype}&{template:atkdmg} {{mod=[[@{dexterity_mod} +@{pb} +5[MAGIC]]]}} {{rname=Suishen ATTACKING}} {{r1=[[@{selected|d20}cs>20 + 8[DEX] + 5[PROF] + 5[MAGIC] ?{Scabbard of Vigor}]]}} @{selected|rtype}cs>20 + 8[DEX] + 5[PROF] + 5[MAGIC] ?{Scabbard of Vigor}]]}} {{attack=1}} {{range=}} {{damage=1}} {{dmg1flag=1}} {{dmg1=[[1d8 + 8[DEX] + 5[MAGIC] ?{Scabbard of Vigor}]]}} {{dmg1type=Slashing}} {{damage=1}} {{dmg2flag=1}} {{dmg2=[[1d6]]}} {{dmg2type=Fire}} {{crit1=[[1d8[CRIT]]]}} {{crit2=[[1d10[CRIT]]]}} 0 {{desc=}}   {{spelllevel=}} {{innate=}} {{globalattack=@{selected|global_attack_mod}}} {{globaldamage=[[0]]}} {{globaldamagecrit=[[0]]}} {{globaldamagetype=@{selected|global_damage_mod_type}}} ammo= @{selected|charname_output}
@{selected|wtype}&{template:atkdmg} {{mod=[[@{dexterity_mod} +@{pb} +5[MAGIC]]]}} {{rname=Suishen ATTACKING}} {{r1=[[@{selected|d20}cs>20 + 8[DEX] + 5[PROF] + 5[MAGIC] ?{Scabbard of Vigor}]]}} @{selected|rtype}cs>20 + 8[DEX] + 5[PROF] + 5[MAGIC] ?{Scabbard of Vigor}]]}} {{attack=1}} {{range=}} {{damage=1}} {{dmg1flag=1}} {{dmg1=[[1d8 + 8[DEX] + 5[MAGIC] ?{Scabbard of Vigor}]]}} {{dmg1type=Slashing}} {{damage=1}} {{dmg2flag=1}} {{dmg2=[[1d6]]}} {{dmg2type=Fire}} {{crit1=[[1d8[CRIT]]]}} {{crit2=[[1d10[CRIT]]]}} 0 {{desc=}}   {{spelllevel=}} {{innate=}} {{globalattack=@{selected|global_attack_mod}}} {{globaldamage=[[0]]}} {{globaldamagecrit=[[0]]}} {{globaldamagetype=@{selected|global_damage_mod_type}}} ammo= @{selected|charname_output}
```

## Suishen double attack (defending) with scabbard of vigor

```roll20
@{selected|wtype}&{template:default} {{Suishen Defending=?{Scabbard of Vigor|Not Active,+0[Scabbard of Vigor not used]|+4 for 1 round,+4[Scabbard of Vigor for 1 round]|+3 for 3 rounds,+3[Scabbard of Vigor for 3 rounds]|+2 for 5 rounds,+2[Scabbard of Vigor for 5 rounds]|+1 for 10 rounds,+1[Scabbard of Vigor for 10 rounds]}}}
@{selected|wtype}&{template:atkdmg} {{mod=[[@{dexterity_mod} +@{pb}]]}} {{rname=Suishen DEFENDING}} {{r1=[[@{selected|d20}cs>20 + 8[DEX] + 5[PROF] ?{Scabbard of Vigor}]]}} @{selected|rtype}cs>20 + 8[DEX] + 5[PROF] ?{Scabbard of Vigor}]]}} {{attack=1}} {{range=}} {{damage=1}} {{dmg1flag=1}} {{dmg1=[[1d8 + 8[DEX] ?{Scabbard of Vigor}]]}} {{dmg1type=Slashing}} {{damage=1}} {{dmg2flag=1}} {{dmg2=[[1d6]]}} {{dmg2type=Fire}} {{crit1=[[1d8[CRIT]]]}} {{crit2=[[1d10[CRIT]]]}} 0 {{spelllevel=}} {{innate=}} {{desc=Suishen is granting AC +5: [[@{AC}+5]]}} ammo @{selected|charname_output}
@{selected|wtype}&{template:atkdmg} {{mod=[[@{dexterity_mod} +@{pb}]]}} {{rname=Suishen DEFENDING}} {{r1=[[@{selected|d20}cs>20 + 8[DEX] + 5[PROF] ?{Scabbard of Vigor}]]}} @{selected|rtype}cs>20 + 8[DEX] + 5[PROF] ?{Scabbard of Vigor}]]}} {{attack=1}} {{range=}} {{damage=1}} {{dmg1flag=1}} {{dmg1=[[1d8 + 8[DEX] ?{Scabbard of Vigor}]]}} {{dmg1type=Slashing}} {{damage=1}} {{dmg2flag=1}} {{dmg2=[[1d6]]}} {{dmg2type=Fire}} {{crit1=[[1d8[CRIT]]]}} {{crit2=[[1d10[CRIT]]]}} 0 {{spelllevel=}} {{innate=}} {{desc=Suishen is granting AC +5: [[@{AC}+5]]}} ammo @{selected|charname_output}
```

## Whispering Shrike (direct call)

```roll20
%{Shadow Moon|repeating_attack_-MqLkrf-cvYSmgMWPLbN_attack}
```

## Shuriken attack or flurry of blows for 1Ki

```roll20
&{template:default} {{?{Action type|Attack Action|Bonus Action (-1Ki)}=Shuriken streak out towards their target(s)}}
%{Shadow Moon|repeating_attack_-McdhGxQ60USI2vlaTz7_attack}
%{Shadow Moon|repeating_attack_-McdhGxQ60USI2vlaTz7_attack}
```

## Stealth check including Pseudodragon (Bitey) with optional Pass Without Trace

```roll20
@{selected|wtype}&{template:atk} {{rname=^{stealth-u}}} {{mod=@{selected|stealth_bonus}?{Pass Without Trace|Inactive,+0[Standard Stealth]|Active,+10[Pass Without Trace]}}} {{r1=[[@{selected|d20}+@{selected|stealth_bonus}@{selected|pbd_safe}?{Pass Without Trace}]]}} @{selected|rtype}+@{selected|stealth_bonus}@{selected|pbd_safe}?{Pass Without Trace}]]}} {{global=@{selected|global_skill_mod}}} @{selected|charname_output} {{desc=[img](https://i.imgur.com/bLzWIBP.gif)}}
@{Pseudodragon|wtype}&{template:npc} @{Pseudodragon|npc_name_flag} {{rname=^{stealth}}} {{mod=@{Pseudodragon|npc_stealth}}} {{r1=[[@{Pseudodragon|d20}+@{Pseudodragon|npc_stealth}?{Pass Without Trace|Inactive|Active}]]}} @{Pseudodragon|rtype}+@{Pseudodragon|npc_stealth}?{Pass Without Trace|Inactive|Active}]]}} {{type=Skill}}
```

## Perception check including Pseudiodragon (Bitey)

```roll20
@{Shadow Moon|perception_roll}
@{Pseudodragon|wtype}&{template:npc} @{Pseudodragon|npc_name_flag} {{rname=^{perception}}} {{mod=@{Pseudodragon|npc_perception}}} {{r1=[[@{Pseudodragon|d20}+@{Pseudodragon|npc_perception}]]}} @{Pseudodragon|rtype}+@{Pseudodragon|npc_perception}]]}} {{type=Skill}}
```

## Boots of Speedy Spider Climbing

```roll20
&{template:spell} {{name=Haste (as Speed)}} {{level=Boots of Speedy Spiderkind}} {{castingtime=click heels (free action)}} {{range=+30 movement}} {{target=self}} {{s=1}} {{duration=10 rounds / day (may be non-consecutive)}} {{description=Click your heels together, Dorothy, and I'll show you how deep the rabbit hole goes. 

On each round this ability is active:
+1 extra attack (target within 30ft of a previous target)
+1 bonus on attack rolls
+1 AC
+1 DEX saves
+30 ft movement}} {{charname=Shadow Moon}}
```

## notes and scribblings on api commands

```roll20
!setattr --sel --silent --repeating_damagemod_$1_global_damage_active_flag|1
!setattr --sel --silent --repeating_damagemod_$1_global_damage_active_flag|1
!setattr --sel --silent --repeating_damagemod_$1_global_damage_active_flag|1
SPEED: 
  GLOBAL SAVE MOD: -MwOCZ978X6LRZT0P1t3
  GLOBAL ATK MOD: -MwOCa1ZsBmoyvT6Mu5b
  GLOBAL AC MOD: -MwOGCNvu-E5v1aWgZ3b
Suishen DEFENDING:
  GLOBAL AC MOD: -MwOCaL5YpqS9l7X5qLs

!setattr --sel --repeating_acmod_-MwOGCNvu-E5v1aWgZ3b_attr_global_ac_active_flag|1
!setattr --sel --repeating_acmod_-MwOGCNvu-E5v1aWgZ3b_global_ac_active_flag|1

!setattr --sel --repeating_acmod_-McdhGxQ60USI2vlaTz7_attr_global_ac_active_flag|1
!setattr --sel --repeating_acmod_$1_global_ac_active_flag|1


!setattr --sel --silent --repeating_damagemod_$1_global_damage_active_flag|1
!setattr --sel --evaluate --attr3|2*%attr1% + 7 - %attr2%
!setattr --sel --evaluate --attr1|%attr1% - 1
!modbattr --sel --arrows|-1
&{template:default} {{name=Cthulhu}} !modattr --silent --charid @{target|character_id} --sanity|-{{Sanity damage=[[2d10+2]]}} --corruption|{{Corruption=Corruption increases by [[1]]}}!!! {{description=Text}}
--charid @{target|character_id}

!setattr --sel --repeating_savemod_$0_global_save_active_flag|1

!setattr --sel --repeating_attackmod_$0_global_attack_active_flag|1

&{template:default} {{name=Cthulhu}} !modattr --silent --charid @{target|character_id} --sanity|-{{Sanity damage=[[2d10+2]]}} --corruption|{{Corruption=Corruption increases by [[1]]}}!!! {{description=Text}}

&{template:default} {{name=Speed Round}} !modattr --silent --charid @{target|character_id} --repeating_resources_-MwDq364TixYlKREk5SP_resource_left|-1!!! {{description=Text}}

!modbattr --sel --silent --repeating_resources_-MwDq364TixYlKREk5SP_resource_left|-1
```
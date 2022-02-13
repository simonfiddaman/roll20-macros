# Shadow Moon macros

## Suishen reference attack

```roll20
@{Shadow Moon|wtype}&{template:atkdmg} {{mod=+17}} {{rname=(AD) Suishen +4}} {{r1=[[@{Shadow Moon|d20}cs>20 + 8[DEX] + 5[PROF] + 4[MAGIC]]]}} @{Shadow Moon|rtype}cs>20 + 8[DEX] + 5[PROF] + 4[MAGIC]]]}} {{attack=1}} {{range=}} {{damage=1}} {{dmg1flag=1}} {{dmg1=[[1d8 + 8[DEX] + 4[MAGIC]]]}} {{dmg1type=Slashing}} {{damage=1}} {{dmg2flag=1}} {{dmg2=[[1d6]]}} {{dmg2type=Fire}} {{crit1=[[1d8[CRIT]]]}} {{crit2=[[1d6[CRIT]]]}} 0 {{desc=}}   {{spelllevel=}} {{innate=}} {{globalattack=@{Shadow Moon|global_attack_mod}}} {{globaldamage=[[0]]}} {{globaldamagecrit=[[0]]}} {{globaldamagetype=@{Shadow Moon|global_damage_mod_type}}} ammo= @{Shadow Moon|charname_output}
```

## Suishen double attack (attacking) with scabbard of vigor

```roll20
@{selected|wtype}&{template:default} {{Suishen Attacking=?{Scabbard of Vigor|Not Active,+0[Scabbard of Vigor not used]|+4 for 1 round,+4[Scabbard of Vigor for 1 round]|+3 for 3 rounds,+3[Scabbard of Vigor for 3 rounds]|+2 for 5 rounds,+2[Scabbard of Vigor for 5 rounds]|+1 for 10 rounds,+1[Scabbard of Vigor for 10 rounds]}}}
@{selected|wtype}&{template:atkdmg} {{mod=[[@{dexterity_mod} +@{pb} +4[MAGIC]]]}} {{rname=Suishen ATTACKING}} {{r1=[[@{selected|d20}cs>20 + 8[DEX] + 5[PROF] + 4[MAGIC] ?{Scabbard of Vigor}]]}} @{selected|rtype}cs>20 + 8[DEX] + 5[PROF] + 4[MAGIC] ?{Scabbard of Vigor}]]}} {{attack=1}} {{range=}} {{damage=1}} {{dmg1flag=1}} {{dmg1=[[1d8 + 8[DEX] + 4[MAGIC] ?{Scabbard of Vigor}]]}} {{dmg1type=Slashing}} {{damage=1}} {{dmg2flag=1}} {{dmg2=[[1d6]]}} {{dmg2type=Fire}} {{crit1=[[1d8[CRIT]]]}} {{crit2=[[1d10[CRIT]]]}} 0 {{desc=}}   {{spelllevel=}} {{innate=}} {{globalattack=@{selected|global_attack_mod}}} {{globaldamage=[[0]]}} {{globaldamagecrit=[[0]]}} {{globaldamagetype=@{selected|global_damage_mod_type}}} ammo= @{selected|charname_output}
@{selected|wtype}&{template:atkdmg} {{mod=[[@{dexterity_mod} +@{pb} +4[MAGIC]]]}} {{rname=Suishen ATTACKING}} {{r1=[[@{selected|d20}cs>20 + 8[DEX] + 5[PROF] + 4[MAGIC] ?{Scabbard of Vigor}]]}} @{selected|rtype}cs>20 + 8[DEX] + 5[PROF] + 4[MAGIC] ?{Scabbard of Vigor}]]}} {{attack=1}} {{range=}} {{damage=1}} {{dmg1flag=1}} {{dmg1=[[1d8 + 8[DEX] + 4[MAGIC] ?{Scabbard of Vigor}]]}} {{dmg1type=Slashing}} {{damage=1}} {{dmg2flag=1}} {{dmg2=[[1d6]]}} {{dmg2type=Fire}} {{crit1=[[1d8[CRIT]]]}} {{crit2=[[1d10[CRIT]]]}} 0 {{desc=}}   {{spelllevel=}} {{innate=}} {{globalattack=@{selected|global_attack_mod}}} {{globaldamage=[[0]]}} {{globaldamagecrit=[[0]]}} {{globaldamagetype=@{selected|global_damage_mod_type}}} ammo= @{selected|charname_output}
```

## Suishen double attack (defending) with scabbard of vigor

```roll20
@{selected|wtype}&{template:default} {{Suishen Defending=?{Scabbard of Vigor|Not Active,+0[Scabbard of Vigor not used]|+4 for 1 round,+4[Scabbard of Vigor for 1 round]|+3 for 3 rounds,+3[Scabbard of Vigor for 3 rounds]|+2 for 5 rounds,+2[Scabbard of Vigor for 5 rounds]|+1 for 10 rounds,+1[Scabbard of Vigor for 10 rounds]}}}
@{selected|wtype}&{template:atkdmg} {{mod=[[@{dexterity_mod} +@{pb}]]}} {{rname=Suishen DEFENDING}} {{r1=[[@{selected|d20}cs>20 + 8[DEX] + 5[PROF] ?{Scabbard of Vigor}]]}} @{selected|rtype}cs>20 + 8[DEX] + 5[PROF] ?{Scabbard of Vigor}]]}} {{attack=1}} {{range=}} {{damage=1}} {{dmg1flag=1}} {{dmg1=[[1d8 + 8[DEX] ?{Scabbard of Vigor}]]}} {{dmg1type=Slashing}} {{damage=1}} {{dmg2flag=1}} {{dmg2=[[1d6]]}} {{dmg2type=Fire}} {{crit1=[[1d8[CRIT]]]}} {{crit2=[[1d10[CRIT]]]}} 0 {{spelllevel=}} {{innate=}} {{desc=Suishen is granting AC +4: [[@{AC}+4]]}} ammo @{selected|charname_output}
@{selected|wtype}&{template:atkdmg} {{mod=[[@{dexterity_mod} +@{pb}]]}} {{rname=Suishen DEFENDING}} {{r1=[[@{selected|d20}cs>20 + 8[DEX] + 5[PROF] ?{Scabbard of Vigor}]]}} @{selected|rtype}cs>20 + 8[DEX] + 5[PROF] ?{Scabbard of Vigor}]]}} {{attack=1}} {{range=}} {{damage=1}} {{dmg1flag=1}} {{dmg1=[[1d8 + 8[DEX] ?{Scabbard of Vigor}]]}} {{dmg1type=Slashing}} {{damage=1}} {{dmg2flag=1}} {{dmg2=[[1d6]]}} {{dmg2type=Fire}} {{crit1=[[1d8[CRIT]]]}} {{crit2=[[1d10[CRIT]]]}} 0 {{spelllevel=}} {{innate=}} {{desc=Suishen is granting AC +4: [[@{AC}+4]]}} ammo @{selected|charname_output}
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
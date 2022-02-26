# Shadow Moon macros

## Suishen (attacking)

When Suishen is in attacking mode, the enhancement bonus is applied to attack and damage rolls.

```roll20
!setattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_acmod_-MwOCaL5YpqS9l7X5qLs_global_ac_active_flag|0
%{-MqL43DfdxRVAwuOc6U2|repeating_attack_-MqLOWBpl20Bt8wZDFri_attack}
```

## Suishen (defending)

When Suishen is in defending mode, the enhancement bonus is not applied to attack or damage rolls, but boosts Shadow Moon's AC instead.

```roll20
!setattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_acmod_-MwOCaL5YpqS9l7X5qLs_global_ac_active_flag|1
%{-MqL43DfdxRVAwuOc6U2|repeating_attack_-MwOLAGI8COvzPHCHfdR_attack}
```

## Whispering Shrike (direct call)

As Whispering Shrike is generally used as the bonus action following Suishen, the global AC mod should not be toggled.

```roll20
%{Shadow Moon|repeating_attack_-MqLkrf-cvYSmgMWPLbN_attack}
```

## Whispering Ki Flurry

```roll20
&{template:default} {{name=Flurry of Blows}} {{weapon=Whispering Shrike (Ki Focussed)}} {{cost=1 Ki point (Bonus Action)}} {{desc=Ki flows through the Whispering Shrike erupts in a Flurry of Blades}} {{Ki=[[@{Shadow Moon|class_resource}-1]] remaining}}
!modbattr --charid -MqL43DfdxRVAwuOc6U2 --silent --class_resource|-1
%{Shadow Moon|repeating_attack_-MqLkrf-cvYSmgMWPLbN_attack}
%{Shadow Moon|repeating_attack_-MqLkrf-cvYSmgMWPLbN_attack}
```

## Shuriken attack 

```roll20
!setattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_acmod_-MwOCaL5YpqS9l7X5qLs_global_ac_active_flag|0
%{-MqL43DfdxRVAwuOc6U2|repeating_attack_-MqLl4atpCZPoiKGquie_attack}
```

## Shuriken Ki Flurry

```roll20
!setattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_acmod_-MwOCaL5YpqS9l7X5qLs_global_ac_active_flag|0
!modbattr --charid -MqL43DfdxRVAwuOc6U2 --silent --class_resource|-1
&{template:default} {{name=Flurry of Blows}} {{weapon=Shadow Moon's Shuriken}} {{cost=1 Ki point (Bonus Action)}} {{desc=Shuriken streak out towards their target(s) in a Flurry of Shuriken}} {{Ki=[[@{Shadow Moon|class_resource}-1]] remaining}}
%{Shadow Moon|repeating_attack_-MqLl4atpCZPoiKGquie_attack}
%{Shadow Moon|repeating_attack_-MqLl4atpCZPoiKGquie_attack}
```

## Pass Without Trace

```roll20
@{Shadow Moon|wtype}&{template:spell} {{level=abjuration 2}} {{name=Pass without Trace}} {{castingtime=1 action}} {{range=Self}} {{target=Self}} {{v=1}} {{s=1}} {{m=1}} {{material=2 Ki points}} {{duration=Up to 1 hour}} {{description=A veil of shadows and silence radiates from you, masking you and your companions from detection. For the duration, each creature you choose within 30 feet of you (including you) has a +10 bonus to Dexterity (Stealth) checks and can’t be tracked except by magical means. A creature that receives this bonus leaves behind no tracks or other traces of its passage.

[img](https://i.imgur.com/bLzWIBP.gif)

[[@{Shadow Moon|class_resource}-2]] Ki points remain.}} {{athigherlevels=}} 0 {{innate=}} {{savedc=}} {{concentration=1}} @{Shadow Moon|charname_output}
!modbattr --charid -MqL43DfdxRVAwuOc6U2 --silent --class_resource|-2
!setattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_skillmod_-MwnGZLF4JYMW5stdXkW_global_skill_active_flag|1
```

## Silence

```roll20
@{Shadow Moon|wtype}&{template:spell} {{level=illusion 2}} {{name=Silence}} {{castingtime=1 action}} {{range=120 feet}} {{target=20-foot-radius sphere centered on a point you choose within range}} {{v=1}} {{s=1}} 0 {{material=2 Ki points}} {{duration=Up to 10 minutes}} {{description=For the duration, no sound can be created within or pass through a 20-foot-radius sphere centered on a point you choose within range. Any creature or object entirely inside the sphere is immune to thunder damage, and creatures are deafened while entirely inside it. Casting a spell that includes a verbal component is impossible there.

[img](https://c.tenor.com/dizPM1QaPzgAAAAC/sweet-dreams-homer.gif)
[img](https://media1.giphy.com/media/xT5LMNDglidxINC8w0/giphy.gif)

[[@{Shadow Moon|class_resource}-2]] Ki points remain.}} {{athigherlevels=}} Yes {{innate=}} {{concentration=1}} @{Shadow Moon|charname_output}
!modbattr --charid -MqL43DfdxRVAwuOc6U2 --silent --class_resource|-2
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

### Speed Round

```roll20
&{template:spell} {{name=Haste (as Speed)}} {{level=Boots of Speedy Spiderkind}} {{castingtime=click heels (free action)}} {{range=+30 movement}} {{target=self}} {{s=1}} {{duration=10 rounds / day (may be non-consecutive) - ***@{Shadow Moon|repeating_resource_-MwDq364TixYlKREk5SP_resource_left} charges remaining today***}} {{description=Click your heels together, Dorothy, and I'll show you how deep the rabbit hole goes. 

On each round this ability is active:
+1 extra attack (target within 30ft of a previous target)
+1 bonus on attack rolls
+1 AC
+1 DEX saves
+30 ft movement

***@{Shadow Moon|repeating_resource_-MwDq364TixYlKREk5SP_resource_left} charges remaining today***
}} {{charname=Shadow Moon}}

!setattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_savemod_-MwOCZ978X6LRZT0P1t3_global_save_active_flag|1
!setattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_tohitmod_-MwOCa1ZsBmoyvT6Mu5b_global_attack_active_flag|1
!setattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_acmod_-MwOGCNvu-E5v1aWgZ3b_global_ac_active_flag|1
!modbattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_resource_-MwDq364TixYlKREk5SP_resource_left|-1
&{template:default} {{name=Speed Round}} {{Charges remaining=[[@{Shadow Moon|repeating_resource_-MwDq364TixYlKREk5SP_resource_left}-1]] }}
```

### Normal Round

```roll20
!setattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_savemod_-MwOCZ978X6LRZT0P1t3_global_save_active_flag|0
!setattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_tohitmod_-MwOCa1ZsBmoyvT6Mu5b_global_attack_active_flag|0
!setattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_acmod_-MwOGCNvu-E5v1aWgZ3b_global_ac_active_flag|0
&{template:default} {{name=Normal Round}} {{Speed boots charges remaining=[[@{Shadow Moon|repeating_resource_-MwDq364TixYlKREk5SP_resource_left}]] }}
```

## Scabbard of Vigor

### Scabbard of Vigor - deactivate

```roll20
!setattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_tohitmod_-MwOFCDnOd-ru7khSNBP_global_attack_active_flag|0
!setattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_damagemod_-MwOFgUNpOGQzC0Kjgdo_global_damage_active_flag|0
!setattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_tohitmod_-MwOFP100nUQkd0J8swZ_global_attack_active_flag|0
!setattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_damagemod_-MwOCaBaZxPW1bOlaXkD_global_damage_active_flag|0
!setattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_tohitmod_-MwOFY5ow-PwsB6GII9i_global_attack_active_flag|0
!setattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_damagemod_-MwOFq1Bu3mu0Q72Ek1W_global_damage_active_flag|0
!setattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_tohitmod_-MwOFaXMrOi36Tp3a4-1_global_attack_active_flag|0
!setattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_damagemod_-MwOFup82yaHr7c7xk3k_global_damage_active_flag|0
&{template:default} {{name=Scabbard of Vigor is inactive}} {{Charges available=@{Shadow Moon|repeating_resource_-MwlazZE7VeaTCDJqStJ_resource_left} / @{Shadow Moon|repeating_resource_-MwlazZE7VeaTCDJqStJ_resource_left|max}}} {{+4 rounds=@{Shadow Moon|repeating_resource_-MwlazZE7VeaTCDJqStJ_resource_left} / @{Shadow Moon|repeating_resource_-MwlazZE7VeaTCDJqStJ_resource_left|max} }} {{+3 rounds=@{Shadow Moon|repeating_resource_-MwlazZE7VeaTCDJqStJ_resource_right} / @{Shadow Moon|repeating_resource_-MwlazZE7VeaTCDJqStJ_resource_right|max} }} {{+2 rounds=@{Shadow Moon|repeating_resource_-Mwlc0wZkohZsQrJvPqm_resource_left} / @{Shadow Moon|repeating_resource_-Mwlc0wZkohZsQrJvPqm_resource_left|max} }} {{+1 rounds=@{Shadow Moon|repeating_resource_-Mwlc0wZkohZsQrJvPqm_resource_right} / @{Shadow Moon|repeating_resource_-Mwlc0wZkohZsQrJvPqm_resource_right|max} }}
```

### Scabbard of Vigor - full reset

```roll20
!setattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_tohitmod_-MwOFCDnOd-ru7khSNBP_global_attack_active_flag|0
!setattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_damagemod_-MwOFgUNpOGQzC0Kjgdo_global_damage_active_flag|0
!setattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_tohitmod_-MwOFP100nUQkd0J8swZ_global_attack_active_flag|0
!setattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_damagemod_-MwOCaBaZxPW1bOlaXkD_global_damage_active_flag|0
!setattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_tohitmod_-MwOFY5ow-PwsB6GII9i_global_attack_active_flag|0
!setattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_damagemod_-MwOFq1Bu3mu0Q72Ek1W_global_damage_active_flag|0
!setattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_tohitmod_-MwOFaXMrOi36Tp3a4-1_global_attack_active_flag|0
!setattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_damagemod_-MwOFup82yaHr7c7xk3k_global_damage_active_flag|0
&{template:default} {{name=Scabbard of Vigor: RESET}} !setattr --reset --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_resource_-MwDq364TixYlKREk5SP_resource_right|{{Charges=@{Shadow Moon|repeating_resource_-MwDq364TixYlKREk5SP_resource_right|max}}} --repeating_resource_-MwlazZE7VeaTCDJqStJ_resource_left|{{+4 rounds=@{Shadow Moon|repeating_resource_-MwlazZE7VeaTCDJqStJ_resource_left|max}}} --repeating_resource_-MwlazZE7VeaTCDJqStJ_resource_right|{{+3 rounds=@{Shadow Moon|repeating_resource_-MwlazZE7VeaTCDJqStJ_resource_right|max}}} --repeating_resource_-Mwlc0wZkohZsQrJvPqm_resource_left|{{+2 rounds=@{Shadow Moon|repeating_resource_-Mwlc0wZkohZsQrJvPqm_resource_left|max}}} --repeating_resource_-Mwlc0wZkohZsQrJvPqm_resource_right|{{+1 rounds=@{Shadow Moon|repeating_resource_-Mwlc0wZkohZsQrJvPqm_resource_right|max}}}!!! {{description=Scabbard of Vigor has been reset}}
```

### Scabbard of Vigor - +4 for 1 round

```roll20
&{template:spell} {{name=Scabbard of Vigor}} {{level=Wonderous Item}} {{target=Suishen}} {{s=1}} {{duration=1 round}} {{description=Once per day, as part of the action of drawing forth the weapon held by the scabbard, the wearer can order it to endow the weapon with a +4 enhancement bonus on attack and damage rolls for 1 round.

***ACTIVE for next [[@{Shadow Moon|repeating_resource_-MwlazZE7VeaTCDJqStJ_resource_left}]] round***}} {{charname=Shadow Moon}}
!modbattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_resource_-MwDq364TixYlKREk5SP_resource_right|-1
!setattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_tohitmod_-MwOFCDnOd-ru7khSNBP_global_attack_active_flag|1
!setattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_damagemod_-MwOFgUNpOGQzC0Kjgdo_global_damage_active_flag|1
!modbattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_resource_-MwlazZE7VeaTCDJqStJ_resource_left|-1
```

### Scabbard of Vigor - +3 for 3 rounds

```roll20
&{template:spell} {{name=Scabbard of Vigor}} {{level=Wonderous Item}} {{target=Suishen}} {{s=1}} {{duration=3 round}} {{description=Once per day, as part of the action of drawing forth the weapon held by the scabbard, the wearer can order it to endow the weapon with a +3 enhancement bonus on attack and damage rolls for 3 rounds.

***ACTIVE for next [[@{Shadow Moon|repeating_resource_-MwlazZE7VeaTCDJqStJ_resource_right}]] rounds***}} {{charname=Shadow Moon}}
!modbattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_resource_-MwDq364TixYlKREk5SP_resource_right|-1
!setattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_tohitmod_-MwOFP100nUQkd0J8swZ_global_attack_active_flag|1
!setattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_damagemod_-MwOCaBaZxPW1bOlaXkD_global_damage_active_flag|1
!modbattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_resource_-MwlazZE7VeaTCDJqStJ_resource_right|-1
```

### Scabbard of Vigor - +2 for 5 rounds

```roll20
&{template:spell} {{name=Scabbard of Vigor}} {{level=Wonderous Item}} {{target=Suishen}} {{s=1}} {{duration=5 round}} {{description=Once per day, as part of the action of drawing forth the weapon held by the scabbard, the wearer can order it to endow the weapon with a +2 enhancement bonus on attack and damage rolls for 5 rounds.

***ACTIVE for next [[@{Shadow Moon|repeating_resource_-Mwlc0wZkohZsQrJvPqm_resource_left}]] rounds***}} {{charname=Shadow Moon}}
!modbattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_resource_-MwDq364TixYlKREk5SP_resource_right|-1
!setattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_tohitmod_-MwOFY5ow-PwsB6GII9i_global_attack_active_flag|1
!setattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_damagemod_-MwOFq1Bu3mu0Q72Ek1W_global_damage_active_flag|1
!modbattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_resource_-Mwlc0wZkohZsQrJvPqm_resource_left|-1
```

### Scabbard of Vigor - +1 for 10 rounds

```roll20
&{template:spell} {{name=Scabbard of Vigor}} {{level=Wonderous Item}} {{target=Suishen}} {{s=1}} {{duration=10 round}} {{description=Once per day, as part of the action of drawing forth the weapon held by the scabbard, the wearer can order it to endow the weapon with a +1 enhancement bonus on attack and damage rolls for 10 rounds.

***ACTIVE for next [[@{Shadow Moon|repeating_resource_-Mwlc0wZkohZsQrJvPqm_resource_right}]] rounds***}} {{charname=Shadow Moon}}
!modbattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_resource_-MwDq364TixYlKREk5SP_resource_right|-1
!setattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_tohitmod_-MwOFaXMrOi36Tp3a4-1_global_attack_active_flag|1
!setattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_damagemod_-MwOFup82yaHr7c7xk3k_global_damage_active_flag|1
!modbattr --charid -MqL43DfdxRVAwuOc6U2 --silent --repeating_resource_-Mwlc0wZkohZsQrJvPqm_resource_right|-1
```
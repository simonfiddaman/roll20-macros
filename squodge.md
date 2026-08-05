# PF2 Roll20 macros for Squodge Baymin

## Medicine Master from Level 7

### Treat Wounds

#### Risky Surgery + Treat Wounds (DC20)

```roll20
@{Squodge|whispertype} &{template:default} {{name=🍄 Risky Surgery + Treat Wounds (DC 20)
}}{{Duration=10 minutes
}}{{targets=up to 4 creatures
}}{{risky surgery=[[1d8cf<8cs9[Slashing]]] 🔪 damage
}}{{Medicine DC 20 🛠️=[[1d20cf0cs>2 + [@{Squodge|medicine_proficiency_display}](@{Squodge|medicine})[@{Squodge|text_modifier}] + (2)[Risky Surgery] ]]
}}{{^{Critical Success}=[^{roll}](`/r 4d8cf0cs>0+10 HP ❤️ recovered) 
}}{{^{Success on 20}=[^{roll}](`/r 2d8cf0cs0+10 HP ❤️ recovered)
}}
```

#### Risky Surgery + Treat Wounds (DC30)

```roll20
@{Squodge|whispertype} &{template:default} {{name=🍄 Risky Surgery + Treat Wounds (DC 30)
}}{{Duration=10 minutes
}}{{targets=up to 4 creatures
}}{{risky surgery=[[1d8cf<8cs9[Slashing]]] 🔪 damage
}}{{Medicine DC 30 🛠️=[[1d20cf1cs>10 + [@{Squodge|medicine_proficiency_display}](@{Squodge|medicine})[@{Squodge|text_modifier}] + (2)[Risky Surgery] ]]
}}{{^{Critical Success on 30+}=[^{roll}](`/r 4d8cf0cs>0+30 HP ❤️ recovered) 
}}{{^{Failure on 22-29}=0 HP recovered
}}{{^{Critical Failure on 21}=[^{roll}](`/r 1d8cf>1cs9 🔪 damage) 
}}
```

### Garden of Healing

```roll20
&{template:default} {{name=🍄 Garden of Healing
}} {{range=?{range|10|15}ft emanation
}} {{healing=[[4d4cf0cs0[Garden of Healing]  +round(@{Squodge|level}/2)[level][Channeler's Stance] +1[Staff of Healing] ]] 
}} {{sustain=1 min / ?{sustained|10|9|8|7|6|5|4|3|2|1|0} more rounds
}}
```

### Battle Medicine

#### Battle Medicine (DC 20)

```roll20
&{template:default} {{name=🍄 Battle Medicine (DC 20) on @{selected|character_name}
}}{{Medicine Check 🛠️=[[1d20cf1cs>12 + [@{Squodge|medicine_proficiency_display}](@{Squodge|medicine})[@{Squodge|text_modifier}] + (@{Squodge|query_roll_bonus})[@{Squodge|text_bonus}] ]]
}}{{^{Critical Success}=[^{roll}](`/r 4d8cf0cs>0+10 HP ❤️ recovered) 
}}{{^{Success [20-30]}=[^{roll}](`/r 2d8cf0cs0+10 HP ❤️ recovered)
}}{{^{Critical Failure on 19}=[^{roll}](`/r 1d8cf>0cs0] 🔪 damage)
}}{{notes=Immune for 1 day
}}
```

#### Battle Medicine (DC 30)

```roll20
&{template:default} {{name=🍄 Battle Medicine (DC 30) on @{selected|character_name}
}}{{Medicine Check 🛠️=[[1d20cf<2cs20 + [@{Squodge|medicine_proficiency_display}](@{Squodge|medicine})[@{Squodge|text_modifier}] + (@{Squodge|query_roll_bonus})[@{Squodge|text_bonus}] ]]
}}{{^{Critical Success on 38}=[^{roll}](`/r 4d8cf0cs>0+30 HP ❤️ recovered) 
}}{{^{Success [30-37]}=[^{roll}](`/r 2d8cf0cs0+10 HP ❤️ recovered)
}}{{^{Failure on [21-29]}=0 HP recovered
}}{{^{Critical Failure on [19-20]}=[^{roll}](`/r 1d8cf>1cs9 🔪 damage) 
}}{{notes= Immune for 1 day
}}
```






## test

### Roll20 Risky Surgery

```roll20
@{Squodge|whispertype} &{template:rolls} {{limit_height=@{Squodge|roll_limit_height}
}} {{charactername=@{Squodge|character_name}
}} {{header=Risky Surgery
}} {{subheader=^{skill_feats}
}} {{info01_name=^{skill}
}} {{info01=Medicine
}} {{info02_name=^{level}
}} {{info02=1
}} {{info03_name=^{traits}
}} {{info03=General, Skill
}} {{info04_name=^{prerequisites}
}} {{info04=trained in Medicine
}} {{info05_name=^{action}
}} {{info05=^{empty-string}
}} {{info06_name=^{trigger}
}} {{info06=
}} {{info07_name=^{requirements}
}} {{info07=
}} {{info08_name=^{frequency}
}} {{info08=
}} {{info09_name=^{benefits}
}} {{info09=Deal damage to a patient to gain +2 to Treat Wounds
}} {{info10_name=^{special}
}} {{info10=
}} {{desc=Your surgery can bring a patient back from the brink of death, but might push them over the edge. When you Treat Wounds, you can deal [[1d8]] (1d8) slashing damage to your patient just before applying the effects of Treat Wounds. If you do, you gain a +2 circumstance bonus to your Medicine check to Treat Wounds, and if you roll a success, you get a critical success instead.
}} {{show_action_icon=@{Squodge|roll_option_action_icon}
}} {{action_icon=empty-string}}
```

```roll20
%{Squodge|MEDICINE}+2
```

```roll20
&{template:default} {{name=🍄 Squodge **Risky Surgery Healing**
}}{{🔪&nbsp;Damage=[[1d8]] Slashing
}}{{🛠️&nbsp;Medicine=[[d20+@{Squodge|medicine}+2]]
}}{{❤️&nbsp;Heal=[[4d8[healing]+10+1]] Healing
}}
```

```roll20
&{template:default} {{name=Battlefield Medicine on ?{Character Healing|0}}} {{Medicine Check=[[1d20cs20cf1 + [@{Selected|medicine_proficiency_display}](@{Selected|medicine})[@{Selected|text_modifier}] + (@{Selected|query_roll_bonus})[@{Selected|text_bonus}]]]}} {{DC=?{Target DC|15|20}}}  {{Critical Success= [[4d8]] HP recovered}}  {{Success=[[2d8]]} HP recovered}} {{Critical Failure= [[1d8]] HP damage}} {{notes= Immune for an hour, and not a day.}}
```

```roll20
&{template:default} {{name=Treat Wounds  on ?{Character Healing|0}}} {{Medicine Check=[[1d20cs20cf1 + [@{Selected|medicine_proficiency_display}](@{Selected|medicine})[@{Selected|text_modifier}] + (@{Selected|query_roll_bonus})[@{Selected|text_bonus}] + (2)]]}} {{DC=?{Target DC|15|20}}}  {{Critical Success DC 15= [[4d8]] HP recovered}}  {{Critical Success DC 20=[[4d8+10]] HP recovered}} {{Critical Failure= [[1d8]] HP damage}} {{Risky Surgery Damage = [[1d8]] damage}} {{notes= Immune for an hour, takes 10 minutes, if continue for an hour double HP recovered.}}
```




```roll20
&{template:default} {{name=Treat Wounds (Trained: DC 15) on ?{Character Healing|Self}
}}{{Risky Surgery Damage = [[1d8]] HP damage
}}{{Medicine Check=[[1d20cs>8 + [@{Selected|medicine_proficiency_display}](@{Selected|medicine})[@{Selected|text_modifier}] + (@{Selected|query_roll_bonus}+2)[@{Selected|text_bonus}] ]]
}}{{Target DC=15
}}{{Critical Success= [[4d8]] HP recovered
}}{{notes= Continuous Healing: not Immune, may be repeated immediately.
}}
```


```roll20
&{template:default} {{name=Treat Wounds (Expert: DC 20) on ?{Character Healing|Self}
}}{{Risky Surgery Damage = [[1d8]] HP damage
}}{{Medicine Check=[[1d20cs>13 + [@{Selected|medicine_proficiency_display}](@{Selected|medicine})[@{Selected|text_modifier}] + (@{Selected|query_roll_bonus}+2)[@{Selected|text_bonus}] ]]
}}{{Target DC=20
}}{{Critical Success= [[4d8+10]] HP recovered
}}{{notes= Continuous Healing: not Immune, may be repeated immediately.
}}
```


```roll20
&{template:default} {{name=Treat Wounds (Master: DC 30) on ?{Character Healing|Self}
}}{{Risky Surgery Damage = [[1d8]] HP damage
}}{{Medicine Check=[[1d20cs>10 + [@{Selected|medicine_proficiency_display}](@{Selected|medicine})[@{Selected|text_modifier}] + (@{Selected|query_roll_bonus}+2)[@{Selected|text_bonus}] ]]
}}{{Target DC=20
}}{{Critical Success= [[4d8+30]] HP recovered
}}{{Critical Failure= [[1d8]] HP damage
}}{{notes= Continuous Healing: not Immune, may be repeated immediately.
}}
```


```roll20
&{template:default} {{name=Treat Wounds  on ?{Character Healing|Self}}} {{Medicine Check=[[1d20cs8 + [@{Selected|medicine_proficiency_display}](@{Selected|medicine})[@{Selected|text_modifier}] + (@{Selected|query_roll_bonus}+2)[@{Selected|text_bonus}] ]]}} {{DC=?{Target DC|15|20}}}  {{Critical Success DC 15= [[4d8]] HP recovered}}  {{Critical Success DC 20=[[4d8+10]] HP recovered}} {{Critical Failure= [[1d8]] HP damage}} {{Risky Surgery Damage = [[1d8]] damage}} {{notes= Continuous Healing: not Immune, may be repeated immediately.}}
```



```roll20
@{Squodge|whispertype} &{template:rolls} {{limit_height=@{Squodge|roll_limit_height}
}} {{charactername=@{Squodge|character_name}
}} {{header=+1 Mighty Striking Thundering Fist Wraps of Booping
}} {{subheader=^{melee_strike}
}} {{notes_show=@{Squodge|roll_show_notes}
}} {{notes=
}} {{roll01_name=^{attack}
}} {{roll01=[[1d20cs20cf1 + [T] 13[@{Squodge|text_modifier}] + (0)[OTHER] + (@{Squodge|query_roll_bonus})[@{Squodge|text_bonus}]]]
}} {{roll01_type=attack
}} {{roll01_info=Agile, Finesse, Invested, Magical, Nonlethal, Unarmed
}} {{roll01_critical=1
}} {{roll02misc=[^{roll} ^{damage}](~-OsBtHKIjhttUGds8oZp|repeating_melee-strikes_-OsBtHzog3qvLQz4p0sk_DAMAGE) 
}} {{roll03misc=[^{roll} ^{critical_damage}](~-OsBtHKIjhttUGds8oZp|repeating_melee-strikes_-OsBtHzog3qvLQz4p0sk_CRITICAL_DAMAGE) }}
```


```roll20
&{template:default} {{name=Battle Medicine (DC 30) on @{selected|character_name}
}}{{Medicine Check=[[1d20cf<2cs20 + [@{Squodge|medicine_proficiency_display}](@{Squodge|medicine})[@{Squodge|text_modifier}] + (@{Squodge|query_roll_bonus})[@{Squodge|text_bonus}] ]]
}}{{Critical Success [38]= [[4d8cf0cs>0+10]] HP recovered
}}{{Success [30-37]= [[2d8cf0cs0+10]] HP recovered
}}{{Critical Failure [<3]= [[1d8cf<8cs9]] damage
}}{{notes= Immune for 1 day
}}
```


```roll20
@{Squodge|whispertype} &{template:rolls} {{limit_height=@{Squodge|roll_limit_height}
}} {{charactername=@{Squodge|character_name}
}} {{header=Battle Medicine (DC 30) on @{selected|character_name}
}} {{subheader=^{Medicine Master}
}} {{notes_show=@{Squodge|roll_show_notes}
}} {{notes=Immune for 1 day
}} {{roll01_name=^{Medicine}
}} {{roll01=[[1d20cf<2cs20 + [@{Squodge|medicine_proficiency_display}](@{Squodge|medicine})[@{Squodge|text_modifier}] + (@{Squodge|query_roll_bonus})[@{Squodge|text_bonus}] ]]
}} {{roll01_type=attack
}} {{roll01_info=healing
}} {{roll01_critical=1
}} {{roll02misc=[^{roll} ^{critical_success}](`/r 4d8cf0cs>0+10 HP recovered) 
}} {{roll03misc=[^{roll} ^{success}](`/r 2d8cf0cs0+10 HP recovered)
}}
```

```roll20
@{Squodge|whispertype} &{template:rolls} {{limit_height=@{Squodge|roll_limit_height}
}} {{charactername=@{Squodge|character_name}
}} {{header=Risky Surgery
}} {{subheader=^{skill_feats}
}} {{info01_name=^{skill}
}} {{info01=Medicine
}} {{info02_name=^{level}
}} {{info02=1
}} {{info03_name=^{traits}
}} {{info03=General, Skill
}} {{info04_name=^{prerequisites}
}} {{info04=trained in Medicine
}} {{info05_name=^{action}
}} {{info05=^{empty-string}
}} {{info06_name=^{trigger}
}} {{info06=
}} {{info07_name=^{requirements}
}} {{info07=
}} {{info08_name=^{frequency}
}} {{info08=
}} {{info09_name=^{benefits}
}} {{info09=Deal damage to a patient to gain +2 to Treat Wounds
}} {{info10_name=^{special}
}} {{info10=
}} {{desc=Your surgery can bring a patient back from the brink of death, but might push them over the edge. When you Treat Wounds, you can deal [[1d8]] (1d8) slashing damage to your patient just before applying the effects of Treat Wounds. If you do, you gain a +2 circumstance bonus to your Medicine check to Treat Wounds, and if you roll a success, you get a critical success instead.
}} {{show_action_icon=@{Squodge|roll_option_action_icon}
}} {{action_icon=empty-string
}}
```


```roll20
@{Squodge|whispertype} &{template:rolls} {{limit_height=@{Squodge|roll_limit_height}
}} {{charactername=@{Squodge|character_name}
}} {{header=Heal
}} {{desc=You channel positive energy to heal the living or damage the undead. If the target is a willing living creature, you restore 1d8 Hit Points. If the target is undead, you deal that amount of positive damage to it, and it gets a basic Fortitude save. The number of actions you spend when Casting this Spell determines its targets, range, area, and other parameters.
[one-action] (somatic) The spell has a range of touch.
[two-actions] (somatic, verbal) The spell has a range of 30 feet. If you're healing a living creature, increase the Hit Points restored by 8.
[three-actions] (material, somatic, verbal) You disperse positive energy in a 30-foot emanation. This targets all living and undead creatures in the burst.
}} {{info01_name=^{action}
}} {{info01=^{1-to-3-actions}
}} {{info02_name=^{cast}
}} {{info02=one to three actions
}} {{info03_name=^{traits}
}} {{info03=healing, positive
}} {{info04_name=^{requirement}
}} {{info04=
}} {{info05_name=^{range}
}} {{info05=varies
}} {{info06_name=^{target}
}} {{info06=1 willing living creature or 1 undead creature
}} {{info07_name=^{area}
}} {{info07=
}} {{info08_name=^{duration}
}} {{info08=
}} @{Squodge|option_spell_heightened} {{info10=Heightened (+1) The amount of healing or damage increases by 1d8, and the extra healing for the 2-action version increases by 8.
}} {{show_action_icon=@{Squodge|roll_option_action_icon}
}} {{action_icon=1-to-3-actions
}}  {{savecriticalsuccess=
}} {{savesuccess=
}} {{savecriticalfailure=
}} {{savefailure=
}}{{subheader=^{ necromancy } ^{divine} ^{spell} ^{level} 1
}} {{savedc=[[23[SPELL DC] + 0[@{Squodge|text_misc}]]]
}} {{savetype=^{fortitude}
}} {{savebasic=true
}} 0 0
```

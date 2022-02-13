# NPC macros

## Wolf Pack Attack

```roll20
&{template:default} {{Wolf Pack Attack=(4d6+4)}}
&{template:npcdmg} {{damage=1}} {{dmg1flag=1}} {{dmg1=[[4d8+4[Piercing]]]}}
&{template:desc} {{desc=If the target is a creature, it must succeed on a DC 14 Strength saving throw or be knocked prone}}
```
## Ameiko squad ranged attack

```roll20
&{template:default} {{Ameiko Squad Attack Ranged=(3d6+5)}}
&{template:npcdmg} {{damage=1}} {{dmg1flag=1}} {{dmg1=[[3d8+5[Piercing]]]}}
```

## Ameiko squad melee attack

```roll20
&{template:default} {{Ameiko Squad Melee Attack=(3d6+5)}}
&{template:npcdmg} {{damage=1}} {{dmg1flag=1}} {{dmg1=[[3d6+5[Slashing]]]}}
```

## Ameiko squad with spellcaster casting (reduced damage output)

```roll20
&{template:default} {{Spellcaster=Casting a high level spell}}
&{template:desc} {{desc=Ameiko, Koya, Luke, or Shaleylu cast a high level spell}}
&{template:default} {{Ameiko Squad Attack Ranged=(2d6+5)}}
&{template:npcdmg} {{damage=1}} {{dmg1flag=1}} {{dmg1=[[2d8+5[Piercing]]]}}
```
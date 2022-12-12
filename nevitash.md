# nevitash macros

## Vigilant Blessing

&{template:traits} {{name=Vigilant Blessing}} {{source=Class:Twilight Domain}} {{description=The night has taught you to be vigilant. As an action, you give one creature you touch (including possibly yourself) advantage on the next initiative roll the creature makes. This benefit ends immediately after the roll or if you use this feature again.}}
@{Nevitash|wtype}&{template:simple} {{rname=^{init-u}}} {{mod=@{Nevitash|initiative_bonus}}} {{r1=[[@{Nevitash|initiative_style}+@{Nevitash|initiative_bonus}@{Nevitash|pbd_safe}[INIT] &{tracker}]]}} {{normal=1}} @{Nevitash|charname_output}

## Wisdom Saving Rolls

@{wtype}&{template:simple} {{rname=^{wisdom-save-u}}} {{mod=@{wisdom_save_bonus}}} {{r1=[[@{1d20,1d20}kh1+@{wisdom_save_bonus}@{pbd_safe}]]}} @{advantagetoggle}+@{wisdom_save_bonus}@{pbd_safe}]]}} {{global=@{global_save_mod}}} @{charname_output}

## Toll the Dead

@{wtype}&{template:atkdmg}{{mod=V,S}}{{rname=Toll the Dead}} {{attack=1}} {{range=60 feet}} {{damage=1}} {{dmg1flag=1}} {{dmg1= [[[[(floor((@{level}+1)/6)+1)]]d?{Are they on Full Health?|No,12|Yes,8}]]}} {{dmg1type=Necrotic}}{{dmg2flag=@{global_damage_mod_type}}}{{dmg2=[[@{global_damage_mod_roll}]]}}{{dmg2type=@{global_damage_mod_type}}}{{save=1}} {{saveattr=Wisdom}} {{savedesc=No Damage}} {{savedc=[[8+@{wisdom_mod}+@{pb}]]}} @{charname_output}

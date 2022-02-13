# Global Macros

## Healing potions

### Our Jade Regent Game

```roll20
&{template:atkdmg}  {{damage=1}} {{dmg1flag=1}} ?{Healing Potion Variety?
|Cure Light Wounds (1d8+4), {{rname=Cure Light Wounds Potion (1d8+4)&#125;&#125;  {{dmg1=[[1d8+4[Healing]]]&#125;&#125;  {{dmg1type=Healing&#125;&#125;
|Cure Moderate Wounds (2d8+5), {{rname=Cure Moderate Wounds Potion (2d8+5)&#125;&#125;  {{dmg1=[[2d8+5[Healing]]]&#125;&#125;  {{dmg1type=Healing&#125;&#125;
|Cure Serious Wounds (3d8+7), {{rname=Cure Serious Wounds Potion (3d8+7)&#125;&#125;  {{dmg1=[[3d8+7[Healing]]]&#125;&#125;  {{dmg1type=Healing&#125;&#125;
|Cure Critical Wounds (4d8+9), {{rname=Cure Critical Wounds Potion (4d4+9)&#125;&#125;  {{dmg1=[[4d8+9[Healing]]]&#125;&#125;  {{dmg1type=Healing&#125;&#125;
}
```

### Complete healing set from the internet

```roll20
&{template:atkdmg}  {{damage=1}} {{dmg1flag=1}} ?{Healing Potion Variety?
|5e Standard (2d4+2), {{rname=5e Standard Healing Potion (2d4+2)&#125;&#125;  {{dmg1=[[2d4+2[Healing]]]&#125;&#125; {{dmg1type=Healing&#125;&#125;
|5e Greater (4d4+4), {{rname=5e Greater Healing Potion (4d4+4)&#125;&#125;  {{dmg1=[[4d4+4[Healing]]]&#125;&#125;  {{dmg1type=Healing&#125;&#125;
|5e Superior (8d4+8), {{rname=5e Superior Healing Potion (8d4+8)&#125;&#125;  {{dmg1=[[8d4+8[Healing]]]&#125;&#125;  {{dmg1type=Healing&#125;&#125;
|5e Supreme (10d4+20),{{rname=5e Supreme Healing Potion (10d4+20)&#125;&#125;  {{dmg1=[[10d4+20[Healing]]]&#125;&#125;  {{dmg1type=Healing&#125;&#125;
|Cure Light Wounds (1d8+4), {{rname=Cure Light Wounds Potion (1d8+4)&#125;&#125;  {{dmg1=[[1d8+4[Healing]]]&#125;&#125;  {{dmg1type=Healing&#125;&#125;
|Cure Moderate Wounds (2d8+5), {{rname=Cure Moderate Wounds Potion (2d8+5)&#125;&#125;  {{dmg1=[[2d8+5[Healing]]]&#125;&#125;  {{dmg1type=Healing&#125;&#125;
|Cure Serious Wounds (3d8+7), {{rname=Cure Serious Wounds Potion (3d8+7)&#125;&#125;  {{dmg1=[[3d8+7[Healing]]]&#125;&#125;  {{dmg1type=Healing&#125;&#125;
|Cure Critical Wounds (4d8+9), {{rname=Cure Critical Wounds Potion (4d4+9)&#125;&#125;  {{dmg1=[[4d8+9[Healing]]]&#125;&#125;  {{dmg1type=Healing&#125;&#125;
|PF2 Minor 4gp (1d8+0), {{rname=PF2 Minor Healing Potion (1d8+0)&#125;&#125;  {{dmg1=[[1d8+0[Healing]]]&#125;&#125;  {{dmg1type=Healing&#125;&#125;
|PF2 Lesser 12gp (2d8+5), {{rname=PF2 Lesser Healing Potion (2d8+5)&#125;&#125;  {{dmg1=[[2d8+5[Healing]]]&#125;&#125;  {{dmg1type=Healing&#125;&#125;
|PF2 Moderate 50gp (3d8+10), {{rname=PF2 Moderate Healing Potion (3d8+10)&#125;&#125;  {{dmg1=[[3d8+10[Healing]]]&#125;&#125;  {{dmg1type=Healing&#125;&#125;
|PF2 Greater 400gp (6d8+20), {{rname=PF2 Greater Healing Potion (6d8+20)&#125;&#125;  {{dmg1=[[6d8+20[Healing]]]&#125;&#125;  {{dmg1type=Healing&#125;&#125;
|PF2 Major 5000gp (8d8+30), {{rname=PF2 Major Healing Potion (8d8+30)&#125;&#125;  {{dmg1=[[8d8+30[Healing]]]&#125;&#125;  {{dmg1type=Healing&#125;&#125;
}
```

## Multi-purpose roller - attributes, saving throws, ability checks

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
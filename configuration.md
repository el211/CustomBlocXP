# Configuration Guide

This guide covers the various configuration options available for the CustomBlockXPPlugin. The configuration is defined in the `config.yml` file located in the `plugins/CustomBlockXPPlugin/` directory.

## Main Configuration Options

```yaml
# Activer ou désactiver l'affichage des messages dans la barre d'action lorsque des récompenses sont données
hotbar_message_enabled: true

# Activer ou désactiver l'affichage de la barre de boss lorsque des récompenses sont données
bossbar_message_enabled: true

# Format du message de la barre d'action par défaut
hotbar_message_format: "{job} XP: {jobsxp}, Money: {money}, Points: {points}"

# Format du message de la barre de boss par défaut
bossbar_message_format: "&a{job} XP: &b{jobsxp}, &aMoney: &b{money}, &aPoints: &b{points}"

# Apparence de la barre de boss
bossbar_color: BLUE   # Couleur de la barre de boss
bossbar_style: SOLID  # Style de la barre de boss
```

XP Values Section
The xp_values section allows you to define rewards, XP, and effects for different blocks.

```yaml
xp_values:
  custom_blocks:my_custom_block:
    name: "Custom Block"
    jobsxp: 5.0
    job: "Miner"
    money: 10.0
    points: 2.0
    cancel-vanilla-drops: true
    soundeffectonmined: "ENTITY_EXPERIENCE_ORB_PICKUP"
    visualeffectonmined: "FLAME"
    bannedtools:
      - "WOODEN_PICKAXE"
    Drops:
      drop1:
        TYPE: "COMMAND"
        DROP: "give %player% minecraft:diamond 1"
        chance: 0.5
        message: "&aYou found a diamond!"
      drop2:
        TYPE: null   # Skip this drop by setting TYPE and DROP to null
        DROP: null
        chance: 0.0
        message: null```

Handling Null Values
You can disable specific drops by setting both TYPE and DROP to null:
 ```yaml
     drop2:
        TYPE: null
        DROP: null
        chance: 0.0
        message: null ```

Sound and Visual Effects:
- soundeffectonmined: The sound effect that is played when the block is broken. Use standard Minecraft sound IDs.
- visualeffectonmined: The particle effect that is displayed when the block is broken. Use standard Minecraft particle IDs.


# sb_therapy
FiveM ESX Physical Therapy Script Overview This script allows players to engage in physical training activities

# Installation Guide for Exercise Training Script

## Requirements

Before installing the script, ensure your FiveM server meets the following requirements:

### Dependencies:

- [ESX Framework](https://github.com/esx-framework/esx_core) (Required for economy system)
- [ox\_lib](https://github.com/overextended/ox_lib) (Optional for progress bar support)
- [okokNotify](https://github.com/okok-projects/okokNotify) (Optional for enhanced notifications)
- [wasabi\_crutch](https://github.com/wasabi-scripts/wasabi_crutch) (Optional for injury recovery support)

### Suggested Scripts for Compatibility:

- **DPEmotes** (for additional animation options)
- **esx\_progressbar** (alternative progress bar solution)

## Installation Steps

### 1. Download & Extract

1. Download the script files (`client.lua` and `server.lua`).
2. Create a new folder in your `resources` directory (e.g., `exercise_training`).
3. Place the `client.lua` and `server.lua` files inside the newly created folder.

### 2. Configure `fxmanifest.lua`

Create an `fxmanifest.lua` file in the same folder with the following content:

```lua
fx_version 'cerulean'
game 'gta5'

author 'YourName'
description 'Exercise Training Script'
version '1.0.0'

shared_scripts {
    '@es_extended/imports.lua',
    'config.lua'
}

client_scripts {
    'client.lua'
}

server_scripts {
    '@es_extended/locale.lua',
    'server.lua'
}

dependency 'es_extended'
```

### 3. Configure `config.lua`

Create a `config.lua` file in the same folder with the following:

```lua
Config = {}
Config.ExerciseCost = 50 -- Cost for training session
Config.ExerciseRadius = 5.0 -- Distance from marker to activate training
Config.Marker = { Position = vector3(-1200.0, -1560.0, 4.0) } -- Change to desired location
Config.ExerciseDuration = 15 -- Time in seconds
Config.HealthGain = 10 -- Health gain after training
Config.UseProgress = true -- Enable progress bar support
Config.ProgressType = "ox" -- Options: "ox", "esx"
Config.UseOkokNotify = true -- Use okokNotify for messages
Config.RemoveCrutch = true -- Remove crutch if wasabi_crutch is installed
Config.Keybind = 38 -- Default keybind (E)
```

### 4. Start the Resource

1. Add the following line to your `server.cfg`:
   ```
   ensure exercise_training
   ```
2. Restart your server or use `refresh` and `ensure exercise_training` in the console.

### 5. Usage

- Go to the configured exercise location.
- type `/PT` to start exercising.
- Pay the required fee and Remove Crutches! (Optional)
- Complete the workout to gain health and stamina.

## Support

For issues or customization requests, feel free to contact the script developer.

Enjoy your training script!



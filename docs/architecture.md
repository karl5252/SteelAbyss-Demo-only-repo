# Steel Abyss – Architecture Overview

Steel Abyss is built using the **Phaser.js** game framework and follows a modular scene-based architecture.

## 🎮 Scene Flow

The game is structured into distinct scenes, managing game lifecycle and progression:

1. **PreloadScene** – loads all assets (sprites, sounds, tilemaps)
2. **MainMenuScene** – displays main menu UI, player options
3. **Stage1Scene** – first level with enemy waves
4. **Stage2Scene** – advanced level with upgraded enemies and new mechanics
5. **VictoryScene / GameOverScene** – final result and restart options

Each scene extends a shared base and uses Phaser's lifecycle methods (`create()`, `update()`, etc.)

## 🧠 Game Logic Components

- **Wave system**: Spawns enemies in timed and patterned sequences, separated from rendering
- **Weapon system**: Modular weapons, upgrades and visual feedback handled via player input and internal cooldowns
- **State machine**: Manages transitions between scenes (e.g., from Stage1 to Stage2 based on boss defeat)
- **Input manager**: Custom handler for keyboard controls and pausing
- **HUD manager**: In-game UI for health, score, wave indicator

## ⚙️ Technical Notes

- Phaser’s built-in loader used for image/audio asset management
- Game runs in fixed update loop (~60fps), collision and physics handled via arcade physics
- Level-specific logic encapsulated to allow for future expansion (e.g. boss fight, cutscenes)

## 🗂️ Folder structure (simplified)

/src
/scenes
PreloadScene.js
MainMenuScene.js
Stage1Scene.js
Stage2Scene.js
VictoryScene.js
GameOverScene.js
/objects
Player.js
Enemy.js
Bullet.js
/utils
InputHandler.js
WaveController.js
/assets
/sprites
/audio
/tilemaps
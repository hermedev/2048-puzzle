# 2048 Puzzle

A Unity implementation of the classic 2048 sliding tile puzzle. Combine equal numbered tiles, grow their values, and try to reach 2048. The project is configured for WebGL and uses Unity's Input System.

## Features

- 4x4 tile board with movement, merging, and score tracking
- Best score saved locally with Unity `PlayerPrefs`
- Keyboard controls: **WASD** or **arrow keys**
- Swipe controls: **touch swipe** on touch devices or **left mouse drag** in desktop browsers
- New Game button and game-over UI
- UI EventSystem configured to use the Input System UI module

## Requirements

- Unity **6000.6.3f1** (project editor version)
- WebGL Build Support module for the Unity Editor if you plan to build for the browser

The Input System and Unity UI packages are declared in `Packages/manifest.json`.

## Open the project

1. Clone or download this repository.
2. In Unity Hub, choose **Add project from disk** and select the repository folder.
3. Open the project with Unity 6000.6.3f1, then wait for packages and assets to import.
4. Open `Assets/Scenes/Game.unity` and press **Play**.

## How to play

Move all tiles in one direction using **W**, **A**, **S**, or **D**, the **arrow keys**, or a swipe/drag across the game board. Tiles with the same value merge when they collide. Each successful move adds a new tile. The game ends when the full board has no available merges. Select **New Game** to start over.

## Build for WebGL

1. Install **WebGL Build Support** for the project's Unity Editor version through Unity Hub.
2. In Unity, open **File > Build Profiles** (called **Build Settings** in some Unity versions) and select **Web** / **WebGL**.
3. Confirm `Assets/Scenes/Game.unity` is included in the build scenes.
4. Select **Build** and choose an output folder, for example `Builds/WebGL`.
5. Run the generated build through a web server or upload it to a host that supports Unity WebGL. Opening `index.html` directly from the file system may not work because browsers restrict local file loading.

The repository is configured with `Assets/Scenes/Game.unity` as its enabled build scene and has WebGL player settings. Test the finished build in target desktop and mobile browsers; browser compatibility and mobile layout have not been documented as verified yet.

## Project layout

```text
Assets/
  Scenes/Game.unity       Main game scene
  Prefabs/Tile.prefab     Tile UI prefab
  TileState/              Tile value and appearance assets
  scripts/                Board, grid, tile, and game manager scripts
  sprites/                Tile graphics
Packages/                 Unity package manifest and lock file
ProjectSettings/          Unity project and build settings
```

## Notes

- Score and best score are stored in the browser/device's local player preferences. They are not synchronized between devices or browsers.
- The project includes the Code Assist editor plugin under `Assets/Plugins/CodeAssist`.
- Generated Unity folders such as `Library`, `Temp`, and `Builds` are excluded through `.gitignore`.

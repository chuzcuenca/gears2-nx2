## Gears of War 2 NX Plus — Fork changes

This fork extends the original project with additional configuration and gameplay selection features.

### Implemented features

- **Level selection:** choose acts, chapters and subchapters directly from the unlock test build. Tested on a real Nintendo Switch.
- **Language configuration:** select the game language independently from the country/region setting through `gears2-nx.toml`.
- **Country configuration:** supports Spain and Mexico without changing the selected language.

### Language and country configuration

The game language and country/region can be configured independently using `gears2-nx.toml`.

The configuration file is located in the same directory as the NRO:

`sdmc:/switch/gears2-nx/gears2-nx.toml`

Edit the `[language]` section to select your preferred settings:

```toml
[language]
user_language = 5
user_country = 71
```

**Supported languages(Included from the game)**

| ID | Language |
|---:|---|
| 1 | English |
| 3 | German |
| 4 | French |
| 5 | Latin American Spanish |
| 6 | Italian |
| 7 | Korean |
| 8 | Traditional Chinese |
| 11 | Polish |
| 12 | Russian |

Language and country are independent settings. Changing the country does not automatically change the selected language.

If the configuration file is missing, cannot be parsed, or contains unsupported values, the game uses the default settings: Latin American Spanish (5) and Mexico (71).

### Experimental build

The first experimental release, `v0.1.0`, includes:

- `gow2-unlock-test.nro`
- `gears2-nx.toml`, configured for Latin American Spanish and Mexico by default.

The original game data and shader files are not included. Users must provide their own legally obtained game files and generate the required shader files.

### Current limitations

Graphics compatibility is still under investigation. Some draw calls are currently discarded, and some shaders are not yet recognized by the renderer. These issues are not fixed in this release.

## SD card installation

Extract the release archive into the root of your Nintendo Switch SD card.

The release provides the following files:

```text
sdmc:/switch/gears2-nx/
    gow2-unlock-test.nro
    gears2-nx.toml
```

### Required user-provided files

This release does not include the original game data or shader files. Users must provide the following files from their own legally obtained copy of Gears of War 2.

**1. Extracted game data**

Place the extracted game files in the `game/` directory:

```text
game/
├── default.xex
└── GearGame/
```

**2. Shader files**

The following files are also required:

- `gow2_shaders.dslib`
- `shadercache_dksh.bin`

These files must be generated using the project's shader extraction and build tools from the user's own game files.

### Final SD card structure

After providing all required files, the directory should look like this:

```text
sdmc:/switch/gears2-nx/
├── gow2-unlock-test.nro
├── gears2-nx.toml
├── gow2_shaders.dslib
├── shadercache_dksh.bin
└── game/
    ├── default.xex
    └── GearGame/
```

Do not download or redistribute game data or shader files from unofficial sources.

### Starting the game

Start it with title takeover: hold R while starting any game, then open the Homebrew Menu.

Applet mode does not provide enough memory.

## Legal

Unofficial fan port with no affiliation to Microsoft or Epic Games. "Gears of War" is a trademark of Microsoft. Users must provide their own legally obtained copy of the game. No game data is included in this fork's releases. The NRO contains recompiled code and the game's shader library. Running homebrew requires custom firmware, which violates Nintendo's terms and can get a console banned.

**Official upstream project.** The original project is maintained at [github.com/VasilkovND/gears2-nx](https://github.com/VasilkovND/gears2-nx). This repository is an independent fork that adds the features documented above.

**Fork releases.** This fork distributes prebuilt experimental NRO files and configuration files through its GitHub Releases. No game data is included. Users must provide their own legally obtained copy of the game. Builds and archives from unofficial third-party sources are not endorsed or verified by this fork.

Source code is under the GPL-3.0 license (see [LICENSE](LICENSE)). The SDK changes are under the SDK's BSD-3-Clause license, and the shader translator changes under MIT.

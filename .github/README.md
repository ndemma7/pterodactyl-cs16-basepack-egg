<div align="center">
 <img align="center" src="https://user-images.githubusercontent.com/5860435/111066129-040e5e00-84f0-11eb-9e1f-7a7e8611da2b.png" alt="Pterodactyl CS 1.6"/>

## Counter-Strike 1.6 BasePack - Pterodactyl Egg

[![Releases](https://img.shields.io/github/v/release/PluginyCS/BasePack)](https://github.com/PluginyCS/BasePack/releases/latest)
[![Discord](https://img.shields.io/discord/1016101167404695653?label=discord)](https://dc.pluginycs.pl)
[![Web](https://img.shields.io/badge/web-pluginycs.pl-brightgreen)](https://pluginycs.pl)

Ready-to-use Pterodactyl egg for Counter-Strike 1.6 servers using [PluginyCS BasePack](https://github.com/PluginyCS/BasePack).

<p align="center">
  <a href="#features">Features</a> ·
  <a href="#installation">Installation</a> ·
  <a href="#configuration">Configuration</a> ·
  <a href="#included-modules">Included Modules</a>
</p>

</div>

---

## Features

- 🚀 **Automatic Installation** - Downloads and configures BasePack in seconds
- 🔐 **Reunion Hash Salt** - Easy configuration via Pterodactyl panel
- 🔧 **Pre-installed Modules** - ReHLDS, ReGameDLL, ReAPI, Metamod-r and more

## Installation

### 1. Import EGG to Pterodactyl

1. Download `egg-counter-strike-1-6-basepack.json`
2. In Pterodactyl admin panel go to: **Nests** → **Import Egg**
3. Select the JSON file and import

### 2. Create Server

1. Create a new server using the imported egg
2. Configure basic parameters:
   - **Map** - Default map (e.g., `de_dust2`)
   - **Reunion Hash Salt** - 32-character hex string (optional)

### 3. Start Server

Start the server - BasePack installation will happen automatically on first run.

## Configuration

### Reunion Hash Salt

Reunion Hash Salt is a 32-character string (hex recommended) used for Steam ID generation. Configure it in Pterodactyl panel or generate your own:
```bash
openssl rand -hex 16
```

Example: `9f3a2b7c1d4e5f6081a2b3c4d5e6f701`

## Included Modules

BasePack includes the following modules (current version: **2.1.0**):

| Module               | Version      | Description                    |
|:---------------------|:-------------|:-------------------------------|
| AMX Mod X            | 1.10.0.5468  | Plugin system                  |
| Metamod-r            | 1.3.0.149    | Plugin loader                  |
| ReHLDS               | 3.14.0.857   | Optimized HLDS engine          |
| ReAPI                | 5.26.0.338   | API for mods                   |
| ReGameDLL            | 5.28.0.756   | Rewritten game logic           |
| Reunion              | 0.2.0.25     | Anti-cheat and authorization   |
| ReVoice Plus         | 2.1.0        | Voice communication            |

### Optional Modules

- Rechecker 2.7
- ReAuthCheck 0.1.6
- WHBlocker 1.5.697
- ReSemiclip 2.4.3
- Hitbox Fixer 1.1.4

## Startup Command
```bash
./hlds_run -console -game cstrike -port 27015 -sport 26900 +map de_dust2 +ip 0.0.0.0 -strictportbind -norestart +maxplayers 32 -pingboost 1 +sys_ticrate 2000 +exec server.cfg -heapsize 65536 -num_edicts 4096 -condebug -master -conclearlog -secure -nobreakpad
```

## Variables

| Name                 | Default Value              | Description                            |
|:---------------------|:---------------------------|:---------------------------------------|
| `HLDS_GAME`          | `cstrike`                  | Game name (do not change)              |
| `SRCDS_MAP`          | `de_dust2`                 | Starting map                           |
| `VAC_PORT`           | `26900`                    | VAC port                               |
| `REUNION_HASH_SALT`  | (empty)                    | Hash salt for Reunion (32 characters)  |

## Troubleshooting

### Server won't start

1. Check installation logs
2. Make sure BasePack was downloaded correctly
3. Verify file permissions

### Reunion warning

If you see a `SteamIdHashSalt` warning, set the value in Pterodactyl panel or edit `reunion.cfg` manually.

## Links

- 📦 [BasePack Repository](https://github.com/PluginyCS/BasePack)
- 🌐 [PluginyCS Website](https://pluginycs.pl)

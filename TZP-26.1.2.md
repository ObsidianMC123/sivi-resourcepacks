# Tissou's Zombie Pack - SIVI 26.1.2

Unofficial compatibility repack. Original assets: **Tissou** and contributors. Upstream 1.21.1 update: **Riku**.

- [Original project](https://www.curseforge.com/minecraft/texture-packs/tissous-zombie-pack-optifine-1-7x-1-20)
- [Upstream file 8547910](https://www.curseforge.com/minecraft/texture-packs/tissous-zombie-repack/files/8547910)
- All original assets remain owned by their creators. This adaptation does not grant a new license to those assets.

## Download

https://raw.githubusercontent.com/ObsidianMC123/sivi-resourcepacks/tzp-26.1.2-v1/tzp-sivi-26.1.2.zip

SHA-1: `a8fecf0c4546820e9ace9f56c53132fac2cd27ed`

Size: 15,056,055 bytes. Resource pack format: 84.0, for Minecraft Java 26.1-26.1.2.

## Changes

- Updated pack.mcmeta to format 84 with min_format/max_format [84,0]; removed legacy supported_formats.
- Lowercased 297 audio file paths and corresponding sound references.
- Converted replace flags from strings to JSON booleans.
- Removed six dangling ambient references: say130, say131, say138, say143, say144, say145.
- Removed the unused malformed assets/minecraft/sounds/mob/sounds.json.
- Added source and author credits. Original PNG and OGG file bytes remain unchanged.

## Client behavior and coexistence

Vanilla clients can use base zombie/husk/drowned/zombie-villager textures and zombie sounds. Random/emissive variants require a compatible client mod such as ETF/OptiFine; this ZIP does not install mods.

Keep ZAS music enabled. Minecraft merges sounds.json per sound event: TZP defines zombie ambient/hurt/death, while ZAS defines 32 music events. They have no shared event keys. The emissive suffix _e matches Catacraft.

Static checks passed: 3,941 ZIP entries, 8 JSON files, 303 existing sound references, archive roundtrip hashes, original texture/audio byte preservation, invalid-ZIP rejection, and comparison against the five configured SIVI packs. All 3,581 PNG images decoded successfully. See tzp-validation.json. In-game validation on vanilla and modded clients is still pending.

## Deferred activation

**Publishing this ZIP does not activate it on the server. No live configuration change, reload, or restart was performed.**

When ready, add the following entry to SiviPack's packs list before sivi-props. This is only a snippet, not a replacement configuration:

```yaml
  - id: tzp-sivi
    url: 'https://raw.githubusercontent.com/ObsidianMC123/sivi-resourcepacks/tzp-26.1.2-v1/tzp-sivi-26.1.2.zip'
    sha1: 'a8fecf0c4546820e9ace9f56c53132fac2cd27ed'
```

Leave all existing pack entries and old release tags unchanged. Apply the server configuration only in an approved test window.

# AGENT.md - AIO-OCIO Project Documentation

This document provides AI agents with context about the AIO-OCIO project structure and configuration.

---

## Project Overview

**AIO-OCIO** (All-In-One OCIO) is an OpenColorIO 2.0+ configuration designed for CG/VFX workflows across multiple software applications including Blender, Maya, Nuke, and Houdini.

**Repository**: https://github.com/RolandVyens/AIO-OCIO (fork of https://github.com/Joegenco/PixelManager/)

---

## Config File Variants

| Config File | Working Space | Target Applications |
|-------------|---------------|---------------------|
| `config_Blender.ocio` | Linear Rec.709 | Blender |
| `config_CG_General.ocio` | ACEScg | Maya, Houdini, general CG |
| `config_COMP_Blender.ocio` | Linear Rec.709 | Compositing with Blender |
| `config_COMP_General.ocio` | ACEScg | Compositing (Nuke, Fusion) |

---

## Directory Structure

```
AIO-OCIO/
├── config_*.ocio          # OCIO config files
├── luts/                   # Core LUTs (AgX, ACES, utility)
├── filmic/                 # Filmic tonemapper LUTs
├── flim/                   # flim tonemapper (silver/default)
├── ARRI/                   # ARRI LogC3/LogC4 transforms
├── Canon/                  # Canon Log transforms
├── Sony/                   # Sony S-Log transforms
├── BMD/                    # Blackmagic Design transforms
├── RWG/                    # RED Wide Gamut transforms
├── OpenDRT/                # Open Display Transform LUTs
├── 2499DRT/                # JP-2499DRT by Juan Pablo Zambrano
├── TCAMv2/                 # FilmLight TCAMv2 transforms
├── TCAMv3/                 # FilmLight TCAMv3 transforms
├── ACES/                   # ACES 2.0 baked LUTs
├── README.md               # English documentation
└── README-Chinese.md       # Chinese documentation
```

---

## Key Color Spaces

### Scene Linear Spaces
- `Linear Rec.709` - Default scene linear (Blender configs)
- `ACEScg` - Academy Color Encoding System (CG General configs)
- `Linear CIE-XYZ E` - Reference space

### Display Transforms (View Transforms)
| Transform | Description |
|-----------|-------------|
| ACES | Academy standard (ACES 1.3) |
| ACES Reference GamutComp | ACES with gamut compression LMT |
| AgX | Default AgX tonemapper |
| AgX Punchy | AgX with punchy look |
| AgX Medium High Contrast | AgX with higher contrast |
| OpenDRT | Jed Smith's Open Display Transform |
| JzDT | Jzazbz-based display transform |
| TCAMv2 | FilmLight's TCAM v2 |
| Filmic | Troy Sobotka's Filmic |
| JP2499DRT | Juan Pablo Zambrano's DRT |
| Khronos PBR Neutral | glTF PBR neutral tonemapper |

### Supported Displays
- sRGB
- Display P3
- Rec.1886
- Rec.2020
- Rec.2100 PQ (1000 nits)
- AdobeRGB

---

## Key Roles

| Role | Color Space | Purpose |
|------|-------------|---------|
| `scene_linear` | Linear Rec.709 | Internal rendering |
| `default` | sRGB | Default colorspace |
| `data` | Non-Color | Data textures (normals, roughness) |
| `aces_interchange` | ACES2065-1 | Cross-config interop |

---

## File Rules (Automatic Color Space Assignment)

| Extension/Pattern | Assigned Color Space |
|-------------------|---------------------|
| `*.tx` | Raw |
| `*.exr` | Linear Rec.709 |
| `*.hdr` | Linear Rec.709 |
| Default | sRGB |

---

## Common Modifications

### Adding a New View Transform
1. Create LUT file in appropriate folder (e.g., `luts/`)
2. Add colorspace definition in `colorspaces:` section
3. Add view entry in each display under `displays:`
4. Update `search_path:` if new folder added
5. Optionally add to `inactive_colorspaces:` presets

### Changing Default Display/View
Edit `active_displays:` and `active_views:` near line 263-267.

### Changing Working Space
Modify `scene_linear` role and related roles in `roles:` section.

---

## OCIO Version Compatibility

- **Minimum**: OCIO 2.0
- **Recommended**: OCIO 2.1+
- Uses `BuiltinTransform` for ACES (requires OCIO 2.0+)

---

## Installation

**For Blender:**
1. Copy all files to `<Blender_datafiles>/colormanagement/`
2. Rename `config_Blender.ocio` → `config.ocio`

**For Other Software:**
- Set environment variable `OCIO` to path of desired config file
- Or configure in application preferences

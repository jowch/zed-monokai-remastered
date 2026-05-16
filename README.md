# Monokai Remastered for Zed

A port of the **Monokai Remastered** color scheme to the [Zed](https://zed.dev) editor, faithful to the version shipped with [Ghostty](https://ghostty.org).

![appearance: dark](https://img.shields.io/badge/appearance-dark-1a1a1a) ![schema: v0.2.0](https://img.shields.io/badge/zed%20schema-v0.2.0-58d1eb)

## What this is

A single Zed theme file — `themes/monokai-remastered.json` — that mirrors Ghostty's bundled `Monokai Remastered` palette and extends it across every UI surface Zed exposes: editor, gutter, tabs, panels, diffs, diagnostics, terminal ANSI, and a full syntax-highlight map.

The 16 ANSI colors, background, foreground, cursor, and selection values are copied verbatim from Ghostty's theme file. Everything else (UI chrome, diff bands, syntax token rules, dim ANSI variants, collaboration cursors) was derived from that palette using Monokai's classic semantic conventions.

## Install

```bash
cp themes/monokai-remastered.json ~/.config/zed/themes/
```

Zed watches `~/.config/zed/themes/` and will pick up the file immediately — no restart needed. Activate with:

- `Cmd+K Cmd+T` (theme selector), or
- Settings → Theme → **Monokai Remastered**

## What was built

| Surface                 | Approach                                                                 |
| ----------------------- | ------------------------------------------------------------------------ |
| Editor + gutter         | `background = #0c0c0c`, foreground `#d9d9d9`, line numbers in dim brown  |
| Syntax (44 token rules) | Classic Monokai semantics — green strings? no, **yellow** strings (`#e0d561`); pink keywords; cyan italic types; orange italic parameters; purple numbers/constants |
| Diff & VCS bands        | Created `#98e024`, Modified `#e0d561`, Deleted `#f4005f`, Renamed `#58d1eb`, all at 13% alpha |
| Diagnostics             | Error/warning/info/success mapped to red/orange/cyan/green ANSI hues     |
| Terminal pane           | All 16 ANSI colors copied from Ghostty; `dim_*` variants synthesized at ~60% luma since Ghostty doesn't expose them |
| Collaboration cursors   | Player 0 uses Ghostty's actual cursor color (`#fc971f`); players 1–7 cycle through the rest of the palette |

The theme validates against Zed's official JSON schema at `https://zed.dev/schema/themes/v0.2.0.json` with zero errors (142 style keys + 44 syntax token rules).

## Palette reference

| Role                         | Hex        | Source ANSI slot |
| ---------------------------- | ---------- | ---------------- |
| Background                   | `#0c0c0c`  | `background`     |
| Foreground / variables       | `#d9d9d9`  | `foreground`     |
| Brightest text               | `#f6f6ef`  | bright_white     |
| Muted text / line numbers    | `#625e4c`  | bright_black     |
| Strings                      | `#e0d561`  | bright_yellow    |
| Numbers, constants, escapes  | `#9d65ff`  | blue (purple)    |
| Keywords, operators, tags    | `#f4005f`  | red / magenta    |
| Functions, attributes        | `#98e024`  | green            |
| Types, properties, info      | `#58d1eb`  | cyan             |
| Parameters, regex, warnings  | `#fd971f`  | yellow           |
| Cursor                       | `#fc971f`  | `cursor-color`   |
| Selection                    | `#343434`  | `selection-background` |

## Licensing

Short version: **you can use, modify, and redistribute this freely.** Long version:

The palette derives from `mbadolato/iTerm2-Color-Schemes`, which is **MIT-licensed** (Copyright © 2011-present Mark Badolato). Ghostty ships an identical copy of the `Monokai Remastered` file from that repo — verified byte-for-byte. The upstream LICENSE explicitly notes:

> The copyright/license for each individual theme belongs to the author of that theme.

So the *collection* is MIT; the individual theme's IP rights belong to its original author. In practice this matters very little here because:

1. The **original Monokai** color scheme was created by **Wimer Hazenberg** in 2006 and has been openly redistributed across hundreds of editors (Sublime Text, VS Code, JetBrains, TextMate, Atom, …) for nearly two decades with no enforcement action.
2. **U.S. copyright law generally does not protect lists of facts** — and a palette is a list of hex values. Specific creative expression (code, visual art, distinctive layouts) can be protected; the bare color values cannot.
3. The Zed JSON file in this repo is an **original work** that *uses* those values; the surrounding structure, syntax-token mapping, UI surface choices, and dim-color derivations are independent design decisions.

To be a good citizen, attribution is included below. No strict legal requirement, but the right thing to do.

### Attribution

- **Monokai (original color scheme)** — Wimer Hazenberg, 2006. [monokai.nl](https://monokai.nl)
- **Monokai Remastered variant + Ghostty `.theme` packaging** — distributed via [mbadolato/iTerm2-Color-Schemes](https://github.com/mbadolato/iTerm2-Color-Schemes) under the MIT License.
- **Ghostty terminal** — used as the immediate source for this port. [ghostty.org](https://ghostty.org)
- **Zed port (this repo)** — derivative JSON authored separately; release under MIT or your license of choice.

If you redistribute this theme as part of a larger work, including the upstream MIT notice from `iTerm2-Color-Schemes` is the cleanest practice.

## File layout

```
zed-monokai-remastered/
├── README.md                          # this file
└── themes/
    └── monokai-remastered.json        # the theme (drop into ~/.config/zed/themes/)
```

## Tweak it

A few decisions that are easy to revisit:

- **Red and magenta are the same hex** (`#f4005f`) in Ghostty's source — faithful to upstream but visually flat in the terminal pane. Swap `terminal.ansi.magenta` to `#ff6188` if you want them distinguishable.
- **Italic types and italic parameters** are the Monokai signature. If you dislike italics in code, remove `"font_style": "italic"` from `type`, `type.builtin`, `variable.parameter`, and `comment`.
- **Dim ANSI colors** were synthesized at ~60% luma. Adjust the `terminal.ansi.dim_*` keys if dimmed terminal output reads wrong in your shell.

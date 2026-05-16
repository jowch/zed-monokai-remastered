# Monokai Remastered for Zed

A port of the **Monokai Remastered** color scheme to [Zed](https://zed.dev), faithful to the version shipped with [Ghostty](https://ghostty.org).

![appearance: dark](https://img.shields.io/badge/appearance-dark-1a1a1a) ![schema: v0.2.0](https://img.shields.io/badge/zed%20schema-v0.2.0-58d1eb) ![license: MIT](https://img.shields.io/badge/license-MIT-98e024)

## Install

```bash
curl -fsSL https://raw.githubusercontent.com/jowch/zed-monokai-remastered/main/themes/monokai-remastered.json \
  -o ~/.config/zed/themes/monokai-remastered.json
```

Zed picks the file up immediately — no restart. Activate with `Cmd+K Cmd+T` and select **Monokai Remastered**.

## Coverage

Editor, gutter, tabs, panels, diffs, diagnostics, terminal ANSI (with dim variants), and a 44-rule syntax map. Validates against [Zed's v0.2.0 theme schema](https://zed.dev/schema/themes/v0.2.0.json).

## Palette

| Role                       | Hex        |
| -------------------------- | ---------- |
| Background                 | `#0c0c0c`  |
| Foreground                 | `#d9d9d9`  |
| Comments                   | `#625e4c`  |
| Strings                    | `#e0d561`  |
| Numbers, constants         | `#9d65ff`  |
| Keywords, operators, tags  | `#f4005f`  |
| Functions                  | `#98e024`  |
| Types, properties          | `#58d1eb`  |
| Parameters                 | `#fd971f`  |
| Cursor                     | `#fc971f`  |
| Selection                  | `#343434`  |

## Customize

The theme is a single JSON file. Edit `~/.config/zed/themes/monokai-remastered.json` directly — Zed reloads it on save.

## Credits

- **Monokai** — Wimer Hazenberg, 2006 ([monokai.nl](https://monokai.nl))
- **Monokai Remastered** — distributed via [mbadolato/iTerm2-Color-Schemes](https://github.com/mbadolato/iTerm2-Color-Schemes) (MIT)
- **Ghostty** — [ghostty.org](https://ghostty.org), the immediate source for this port

## License

[MIT](./LICENSE)

# Version 14 Theme for Starship

A [Starship](https://starship.rs) prompt palette built around the **Version 14** brand palette — the same palette used across the [Zed](https://github.com/version14/zed-theme), [VS Code](https://github.com/version14/vscode-theme), [Neovim/Vim](https://github.com/version14/nvim-theme), and [Ghostty](https://github.com/version14/ghostty-theme) ports.

## Variants

| Variant | File | `palette` value |
|---|---|---|
| **Version 14** | `version14.toml` | `version14` |
| **Version 14 Black** | `version14-black.toml` | `version14-black` |
| **Version 14 Light** | `version14-light.toml` | `version14-light` |

> The `accent`/`cyan` violet is currently a **placeholder** hue, standing in for a retired lime-green accent while a permanent replacement is chosen.

## Installation

1. Paste the contents of the variant file you want into your `~/.config/starship.toml` (or clone the repo — `git clone https://github.com/version14/starship-theme` — to grab all three at once).
2. Set the active palette:
   ```toml
   palette = "version14"
   ```
3. Reference palette colors in your module styles with `$role`, e.g. `style = "bold $accent"`.
4. Open a new shell, or run `starship prompt --path ~` to sanity-check the config parses without errors before relying on a full new shell session.

### Example module styles

```toml
"$schema" = 'https://starship.rs/config-schema.json'

palette = "version14"
add_newline = false

format = """
$directory$git_branch$git_status$cmd_duration
$character"""

[directory]
style = "bold $accent"
truncation_length = 3
truncate_to_repo = false
format = "[$path]($style) "

[git_branch]
symbol = " "
style = "$accent"
format = "[$symbol$branch(:$remote_branch)]($style) "

[git_status]
style = "$fg_muted"
conflicted = "[~]($red)"
ahead = "[⇡${count}]($accent)"
behind = "[⇣${count}]($yellow)"
diverged = "[⇕⇡${ahead_count}⇣${behind_count}]($red)"
untracked = "[?]($fg_muted)"
stashed = "[*]($cyan)"
modified = "[!]($yellow)"
staged = "[+]($green)"
renamed = "[»]($cyan)"
deleted = "[✘]($red)"
format = "[$all_status$ahead_behind]($style) "

[cmd_duration]
min_time = 2_000
style = "$fg_muted"
```

## Color Roles

### `version14`

| Role | Color |
|---|---|
| `bg` | `#1A1E23` |
| `bg_elevated` | `#14171B` |
| `fg` | `#F2F4F6` |
| `fg_muted` | `#6E737A` |
| `accent` (placeholder) | `#B7A2FF` |
| `red` | `#FF5C59` |
| `green` | `#4BDE7F` |
| `yellow` | `#FFA85E` |
| `blue` | `#78AFFF` |
| `magenta` | `#ED8EF3` |
| `cyan` | `#B7A2FF` |
| `border` | `#1A1E23` |

### `version14-black`

| Role | Color |
|---|---|
| `bg` | `#0C0D0E` |
| `bg_elevated` | `#000000` |
| `fg` | `#F2F4F6` |
| `fg_muted` | `#6E737A` |
| `accent` (placeholder) | `#B7A2FF` |
| `red` | `#FF5C59` |
| `green` | `#4BDE7F` |
| `yellow` | `#FFA85E` |
| `blue` | `#78AFFF` |
| `magenta` | `#ED8EF3` |
| `cyan` | `#B7A2FF` |
| `border` | `#0F0F10` |

### `version14-light`

| Role | Color |
|---|---|
| `bg` | `#F4F5F6` |
| `bg_elevated` | `#EBEDEF` |
| `fg` | `#0D0F11` |
| `fg_muted` | `#636870` |
| `accent` (placeholder) | `#5F3BBB` |
| `red` | `#B91A25` |
| `green` | `#166534` |
| `yellow` | `#8F4400` |
| `blue` | `#0054CB` |
| `magenta` | `#8C2293` |
| `cyan` | `#5F3BBB` |
| `border` | `#D2D4D7` |

## Also available for Zed, VS Code, Neovim/Vim, and Ghostty

- [Zed extension](https://github.com/version14/zed-theme)
- [VS Code extension](https://github.com/version14/vscode-theme)
- [Neovim/Vim plugin](https://github.com/version14/nvim-theme)
- [Ghostty theme](https://github.com/version14/ghostty-theme)

## License

[MIT](./LICENSE) © [Mathieu Souflis](https://mathieusouflis.fr)

# dotfiles

Personal configuration files for an Arch Linux desktop running the Hyprland Wayland compositor with a Catppuccin Mocha theme.

**Note:** This is a fork of [`typecraft-dev/dotfiles`](https://github.com/typecraft-dev/dotfiles) adapted by me. It has no license file; the upstream project's terms apply to the forked material.

## Contents

Each top-level directory is a package that mirrors the home directory layout (for example `nvim/.config/nvim/init.lua` belongs at `~/.config/nvim/init.lua`), which is compatible with [GNU Stow](https://www.gnu.org/software/stow/). The repository does not document Stow itself, so that is a suggestion.

- **`hyprland`** — `hyprland.conf` and `hypridle.conf`; sets `$terminal = ghostty`, `$fileManager = nautilus`, `$menu = wofi --show drun`, `$mainMod = super`, and starts waybar, swaync, hyprpaper and hypridle.
- **`hyprmocha`, `hyprlock`, `hyprpaper`, `backgrounds`** — Catppuccin Mocha colors, lock screen, wallpaper daemon and wallpaper images.
- **`waybar`** — status bar (`config.jsonc`, `style.css`, `mocha.css`).
- **`wofi`, `rofi`** — launchers (rofi has a `catppuccin-mocha.rasi` theme).
- **`ghostty`, `kitty`, `alacritty`** — terminal configs (Alacritty with a Catppuccin Mocha theme).
- **`tmux`, `zshrc`, `starship`** — `~/.tmux.conf`; `~/.zshrc` (Starship and zoxide init, `EDITOR=nvim`, history settings, Go in `PATH`); Starship prompt.
- **`nvim`** — Neovim in Lua with lazy.nvim: mason + nvim-lspconfig, nvim-cmp + LuaSnip, treesitter, telescope/snacks, oil.nvim, catppuccin, vim-tmux-navigator, vim-test, GitHub Copilot and avante.nvim, among others (`lazy-lock.json` included).
- **`i3`, `polybar`, `picom`, `screenlayout`, `xresources`** — legacy X11 setup, including xrandr scripts (`4by3.sh`, `16by10.sh`) and `.Xresources`.

## Installation

Install the programs you want (for example `hyprland`, `waybar`, `ghostty`, `neovim`, `tmux`, `zsh`, `starship`, `zoxide`, `stow`), then:

```bash
git clone https://github.com/ralvarezdev/dotfiles.git ~/dotfiles
cd ~/dotfiles
stow hyprland hyprmocha waybar ghostty nvim zshrc starship tmux
```

Back up existing files first; Stow refuses to overwrite them.

## Notes

- Paths and settings (monitor layout, cursor theme `catppuccin-mocha-dark-cursors`, polkit agent path) are tuned for my machine and may need adjusting.
- The Neovim config enables AI-assistant plugins (Copilot, avante.nvim) that need their own authentication.

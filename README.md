# Tmux Session (and Window) Handler
A Tmux plugin that seamlessly integrates [FZF](https://github.com/junegunn/fzf) for fuzzy finding _named_ windows and sessions.

## Requirements
- [FZF](https://github.com/junegunn/fzf)
- [TPM](https://github.com/tmux-plugins/tpm)

## Installation
> [!IMPORTANT]
> Using **TPM**
```conf
set -g @plugin "Jiostorm/tmux-session-handler"
```

## Usage
### Keybindings
> [!IMPORTANT]
> Does not override `<prefix>s` and `<prefix>w` keybindings by default 
```conf
set -g @tmux_fzf_session_keybind "M-s"
set -g @tmux_fzf_window_keybind "M-w"
```

### Options
> [!NOTE]
> All option values defined are by _default_, it can be modified to your liking

#### Popup Position
```conf
set -g @tmux_fzf_x C
set -g @tmux_fzf_y C
```

#### Session Popup Resolution
```conf
set -g @tmux_fzf_session_width 45
set -g @tmux_fzf_session_height 15
```

#### Window Popup Resolution
```conf
set -g @tmux_fzf_window_width 45
set -g @tmux_fzf_window_height 15
```

#### String Formatting
> [!TIP]
> Refer to [Scripting](https://github.com/tmux/tmux/wiki/Advanced-Use#scripting-tmux) section of the Tmux Documentation for more formatting explanation

```conf
set -g @tmux_fzf_session_format "#{p8:[#{session_windows}]}#S"
set -g @tmux_fzf_window_format "#S:#{p8:#{window_index}}${tab}[#W]"
```

#### FZF Options
> [!TIP]
> Refer to `man fzf` or `fzf --help` for more information regarding its options

```conf
set -g @tmux_fzf_session_opts "--style default --layout default --cycle"
set -g @tmux_fzf_window_opts "--style default --layout default --cycle"
```

## Tip(s)
> [!TIP]
> To enable automatic renaming of windows

```conf
set -g automatic-rename on
set -g automatic-rename-format "#{b:pane_current_path}"
```

## [License](LICENSE)

The MIT License (MIT)

Copyright (c) 2025 Jiostorm

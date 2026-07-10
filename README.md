# tmux config

Personal tmux configuration using [TPM](https://github.com/tmux-plugins/tpm) for plugin management and the [Tokyo Night](https://github.com/janoamaral/tokyo-night-tmux) theme.

## Install

```sh
git clone --recurse-submodules git@github.com:chriscborg/tmux.git ~/.config/tmux
```

If already cloned without submodules:

```sh
git submodule update --init --recursive
```

Then start tmux and press `prefix + I` to have TPM install any missing plugins.

## Plugins

- [tpm](https://github.com/tmux-plugins/tpm) — plugin manager
- [tmux-sensible](https://github.com/tmux-plugins/tmux-sensible) — sane defaults
- [tmux-yank](https://github.com/tmux-plugins/tmux-yank) — copy to system clipboard
- [tokyo-night-tmux](https://github.com/janoamaral/tokyo-night-tmux) — theme

## Key bindings

Prefix is remapped from `C-b` to `C-Space`.

| Binding | Action |
| --- | --- |
| `prefix + c` | New window, opened in the current pane's path |
| `prefix + "` | Horizontal split, opened in the current pane's path |
| `prefix + %` | Vertical split, opened in the current pane's path |
| `prefix + h/j/k/l` | Move between panes (vi-style) |
| `prefix + H/J/K/L` | Resize pane (repeatable) |
| Mouse | Enabled for pane selection, resizing, and scroll |
| Copy mode `y` | Copy selection to macOS clipboard (`pbcopy`) |

Copy mode uses vi key bindings.

## Custom commands

Custom command aliases (type these at the tmux command prompt, `prefix + :`):

| Command | Runs |
| --- | --- |
| `dlogs` | `docker logs -f $(docker ps -lq)` |
| `run-ios` | `bundle exec fastlane debug` |
| `run-ios-staging` | `bundle exec fastlane staging` |
| `run-ios-simulator` | `bundle exec fastlane simulator` |
| `deploy-ios-` | `bundle exec fastlane beta` |
| `kill-port` | `kill -9 $(lsof -t -i:3000)` |

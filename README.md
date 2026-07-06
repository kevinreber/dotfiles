# dotfiles

My personal macOS dotfiles, managed with [chezmoi](https://www.chezmoi.io/).

Configs for zsh, tmux, git, Neovim, Ghostty, and npm. Bootstrapped as part of
my [`personal-setup`](https://github.com/kevinreber/personal-setup) repo, which
handles Homebrew packages, SSH/git setup, and the rest of a fresh-machine install.

## Apply on a new machine

```bash
# chezmoi pulls this repo and applies the configs
chezmoi init --apply kevinreber
```

## How it's organized

chezmoi stores each file with a prefix that encodes its destination and mode:

| Source | Applies to |
|--------|-----------|
| `dot_zshrc` | `~/.zshrc` |
| `dot_config/nvim/` | `~/.config/nvim/` |
| `private_dot_ssh/private_config` | `~/.ssh/config` (chmod 600) |

## Secrets

No secrets live in this repo. Machine-local secrets (API keys, tokens) stay in
`~/.zshenv.local`, which is never tracked — `dot_zshenv` just sources it if present.

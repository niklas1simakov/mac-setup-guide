[README](../../README.md) > [Developer Overview](developer_overview.md)

# Developer Overview

## Terminal

### Terminal Selection

- [ ] Default Terminal (free) - Preinstalled on macOS
- [ ] (recommended) [Ghosty](https://ghostty.org/) (free) - Fast and open source terminal with a lot of features
  - read docs for customization
- [ ] [iTerm2](https://iterm2.com/) (free) - Alternative to the default terminal

### Oh My Zsh

- [ ] [Oh My Zsh](https://ohmyz.sh/) (free) - Open source shell framework for managing your shell configuration
- [ ] [Oh My Zsh Plugins](https://github.com/ohmyzsh/ohmyzsh/wiki/Plugins) (free) - Plugins for Oh My Zsh

### Xcode Command Line Tools

Required for a lot of tools to work.

- [ ] Install: `xcode-select --install`

### Homebrew - essential package manager for macOS

- [ ] [Homebrew](https://brew.sh/) (free) - Package manager for macOS
- [ ] (optional) Update basic packages and manage with brew package manager:
  ```sh
  brew install git  # upgrade to latest
  brew install git-lfs  # track large files in git https://github.com/git-lfs/git-lfs
  brew install wget
  brew install zsh  # zshell
  brew install tree
  brew install curl  # to get the latest version of curl
  brew link curl --force
  brew install trash  # move to osx trash instead of rm
  ```
- [ ] (optional) Install some other packages:
  ```sh
  # to be added
  ```

### Generate SSH keys (& signing keys)

#### Generate in terminal

Here a detailed guide on how to generate SSH keys and add them to GitHub.
[Github SSH keygen guide](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

- [ ] Generate keypair
- [ ] Get public key
- [ ] Add public key to GitHub
- [ ] Make sure the SSH key is added to the SSH agent
- [ ] Run `ssh -T git@github.com` to test the connection

#### Generate & Store in 1Password (paid) (my preferred method)

Generate & store keys with a click of button when adding them in the browser. Securely commit with fingerprint instead of password. You keys are securely stored in 1Password and can be accessed from any device where you have 1Password installed.

- [ ] Generate & store keys with a click of button when adding them in the browser (add public key to GitHub)
- [ ] Setup 1Password SSH Agent ([check docs](https://support.1password.com/developer/))
- [ ] Setup SSH config
  - if you have multiple SSH keys for the same service or if you have a lot of keys
  - Export public keys from 1Password to the `~/.ssh/` directory
  - Add the public keys to the SSH config
  - Example:

```sh
# ~/.ssh/config
# Personal GitHub
Host personalgit
	HostName github.com
	User git
	IdentityFile ~/.ssh/personal_git.pub
	IdentitiesOnly yes

# Work GitHub
Host workgit
	HostName github.com
	User git
	IdentityFile ~/.ssh/work_git.pub
	IdentitiesOnly yes
```

### Setup git user info

- [ ] `git config --global user.name "Your Name"`
- [ ] `git config --global user.email "your.email@example.com"`
- [ ] Add signing key to git (you can also add it to 1Password and use the same command)
  - `git config --global user.signingkey <key>`
  - `git config --global commit.gpgsign true`

## IDEs

- [ ] (recommended) [Cursor](https://www.cursor.com/) (free, $ premium subscription) - Code editor with AI agent
- [ ] [Windsurf](https://codeium.com/windsurf) (free, $ premium subscription) - Code editor with AI agent
- [ ] [Trae](https://www.trae.ai/) (currently free) - Code editor with AI agent (by ByteDance, parent company of TikTok)
- [ ] [VSCode](https://code.visualstudio.com/) (free)
- [ ] [IDEs from JetBrains](https://www.jetbrains.com/) ($ subscription) - JetBrains family of IDEs (IntelliJ IDEA, PyCharm, RubyMine, CLion, AppCode)

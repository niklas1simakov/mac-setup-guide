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

- [ ] (recommended) Install node.js and package managers

  ```sh
  brew install fnm # node.js version manager
  fnm install --lts # install latest stable version of node.js & npm
  fnm use --lts # use the latest stable version of node.js

  # alternative package managers (use corepack (bundeled with node.js) to install them)
  corepack enable yarn  # alternative to npm (optional)
  corepack enable pnpm  # alternative to npm or yarn (recommended)

  # check installation & versions
  node -v # check node.js version
  npm -v # check npm version
  yarn -v # check yarn version
  pnpm -v # check pnpm version
  ```

- [ ] (recommended) Install python (with [uv](https://docs.astral.sh/uv/))

  I recommend using [`uv`](https://docs.astral.sh/uv/) to install python and all python packages. It's a modern package manager for python that is faster and more efficient than the default package manager. And you will able to avoid a lot of issues with dependencies. I don't recommend installing python directly with brew. Other options that are popular are `pyenv`, `miniconda` or `poetry` (also a good option), but uv is way more performant and my recommendation.

  ```sh
  brew install uv
  ```

  Explore uv docs for usage details. [`uv` docs](https://docs.astral.sh/uv/)

- [ ] (recommended) Install [Docker Desktop](https://docs.docker.com/desktop/setup/install/mac-install/)

  I recommend using [Docker Desktop](https://docs.docker.com/desktop/setup/install/mac-install/) to install docker and not homebrew, as docker requires a lot of permissions and additional packaged and it's easier to manage with the installer.

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
- [ ] [Visual Studio Code (short: VSCode)](https://code.visualstudio.com/) (free)
- [ ] [IDEs from JetBrains](https://www.jetbrains.com/) ($ subscription) - JetBrains family of IDEs (IntelliJ IDEA, PyCharm, RubyMine, CLion, AppCode)
- [ ] (recommended for iOS development) [Xcode](https://developer.apple.com/xcode/) (free) - Apple IDE for iOS, iPadOS, watchOS, tvOS and macOS development, includes Apple iPhone and iPad emulators
- [ ] (recommended for Android development) [Android Studio](https://developer.android.com/studio) (free) - Android IDE for Android development, includes Android emulator

# `~/.dotfiles`

1. Install Apple's Command Line Tools, which are prerequisites for Git and Homebrew.
```sh
xcode-select --install
```

 2. Clone repo into a new hidden directory.
```sh
# Use SSH (if set up)...
git clone git@github.com:skekcoon/dotfiles.git ~/.dotfiles

# ...or use HTTPS and swotches remote later
git clone https://github.com/skekcoon/dotfiles.git ~/.dotfiles
```

3. Create symlinks in the Home directory to the real files int the repo.
```sh
# There are better an less manual ways to do this;
# investigate install scripts and bootstrapping tools.

ln -s ~/.dotfiles/.zshrc ~/.zshrc
ln -s ~/.dotfiles/.gitconfig ~/.gitconfig
```

4. Install Homebrew, followed by the software listed in the Brewfile.
```sh
# This could also be in an install script.

# Install Homebrew
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Then pass in the Brewfile location...
brew bundle --file ~/.dotfiles/Brewfile

# ...or move to the directory first.
cd ~/.dotfiles && brew bundle
```

## TODO List

- Learn how tu use `defaults` to record and restore System Preferences and other macOS configurations.
- Organize these growing steps into multiple scripts.
- Automate symlinks and run script files with a boostrapping tool like [dotbot](https://github.com/anishathalye/dotbot) or [GNU Stow](https://www.gnu.org/software/stow/).
- Make a checklist of steps to decommission your computer before wiping your hard drive.
- Create a [bootable USB installer for macOS](https://support.apple.com/en-us/101578).
- Integrate other cloud services into your Dotfiles process (Dropbox, Google Drive, etc.).
- Find inspiration and examples in other Dotfiles repositories at [dotfiles.github.io](https://dotfiles.github.io/).

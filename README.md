# `~/.dotfiles`

## macOS

Install Apple's Command Line Tools, which are prerequisites for Git and
Homebrew.
  ```sh
  xcode-select --install
  ```

## On Linux

📦 Update your machine
  ```sh
  sudo apt update -y && sudo apt full-upgrade -y && sudo apt autoremove -y && sudo apt autoclean -y && apt install build-essential
  ```

**Install and set up zsh as default.**
  ```sh
  sudo apt install zsh && zsh --version
  # Expected result: zsh 5.9 or more recent

  # Make it default shell
  chsh -s $(which zsh)
  ```
  
**Restart you machine to use the new default shell. To test if it worked:**
  ```sh
  echo $SHELL
  # Expected result: /bin/zsh or similar.
  ```

1. **Clone repo into a new hidden directory**.
  ```sh
  # Use SSH (if set up)...
  git clone git@github.com:skekcoon/dotfiles.git ~/.dotfiles

  # ...or use HTTPS and switches remote later
  git clone https://github.com/skekcoon/dotfiles.git ~/.dotfiles
  ```

2. **Install Homebrew followed by the software listed in the Brewfile…**
  ```sh
  # Install Homebrew
  /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
  
  # Then pass in the Brewfile location...
  brew bundle --file ~/.dotfiles/Brewfile
  ```

**Stow everything in place.**
  ```sh
  # Make sure to be in ~/.dotfiles to run:
  stow .
  ```

## TODO List
- Learn how tu use `defaults` to record and restore System Preferences and other macOS configurations.
- Organize these growing steps into multiple scripts.
- Automate symlinks and run script files with a boostrapping tool like [dotbot](https://github.com/anishathalye/dotbot) or [GNU Stow](https://www.gnu.org/software/stow/).
- M@ake a checklist of steps to decommission your computer before wiping your hard drive.
- Create a [bootable USB installer for macOS](https://support.apple.com/en-us/101578).
- Integrate other cloud services into your Dotfiles process (Dropbox, Google Drive, etc.).
- Find inspiration and examples in other Dotfiles repositories at [dotfiles.github.io](https://dotfiles.github.io/).

## Tools.list
- [ ] ghostty
- [ ] bitwarden
- [x] [netcat](https://formulae.brew.sh/formula/netcat#default)
- [x] [nmap](https://formulae.brew.sh/formula/nmap#default)
wireshark
tcpdump
hashcat
ffuf
gobuster
hydra
zaproxy
proxychains
sqlmap
radare2
metasploit-framework
python2.7
python3
spiderfoot
theharvester
remmina
xfreerdp
rdesktop
crackmapexec
exiftool
curl
seclists
testssl.sh
- [x] ~vim~ [neovim](https://formulae.brew.sh/formula/neovim#default)
- [x] [openvpn](https://formulae.brew.sh/formula/openvpn#default)


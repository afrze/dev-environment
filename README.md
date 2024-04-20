# Development Environment Setup

This repository contains all the development environment setting, color themes, terminal setups, code editor setups etc.

This setup uses `tmux`, `neovim`, `lazy-vim`

<details>
<summary>Terminal setup for Mac</summary>

**Homebrew Setup**

**Install Homebrew**
Run this command

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

**Add Homebrew to path**
After installing, add it to the path (replace `[username]` with your actual username):

```bash
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/[username]/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"
```

**Install Iterm2**
To install, run:

```bash
brew install --cask iterm2
```

**Install Oh My Zsh**
Run this to install Oh My Zsh:

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

**Install PowerLevel10K Theme for Oh My Zsh**
Run this to install PowerLevel10K:

```bash
git clone https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
```

Now that it’s installed, open the `~/.zshrc` file with your preferred editor and change the value of `ZSH_THEME` as shown below:

```bash
ZSH_THEME="powerlevel10k/powerlevel10k"
```

To reflect this change on your terminal, restart it or run this command:

```bash
source ~/.zshrc
```

To reconfigure terminal theme run

```bash
p10k configure
```

**Iterm Theme**
Please refer `nightly.itermcolors` file.
You can find other themes here: [Iterm2 Color Schemes](https://iterm2colorschemes.com/)

**Change iTerm2 Colors to My Custom Theme**

- Open iTerm2
- Download my color profile by running the following command (will be added to Downloads folder):

```bash
curl https://raw.githubusercontent.com/afrze/dev-environment/main/nightly.itermcolors --output ~/Downloads/nightly.itermcolors
```

- Open iTerm2 preferences
- Go to Profiles > Colors
- Import the downloaded color profile (nightly)
- Select the color profile (nightly)

**Install ZSH Plugins**
Install zsh-autosuggestions:

```bash
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

Install zsh-syntax-highlighting:

```bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

Open the `~/.zshrc` file in your desired editor and modify the plugins line to what you see below.

```bash
plugins=(git zsh-autosuggestions zsh-syntax-highlighting web-search)
```

Load these new plugins by running:

```bash
source ~/.zshrc
```

</details>

<details>
<summary>Terminal setup for Linux</summary>

**Install zsh**

*For Fedora*

1. Install Zsh: You can install Zsh using the following command in the terminal:

```bash
sudo dnf install zsh
```

2.Verify Installation: After installation, verify the version of Zsh by running the following command:

```bash
zsh --version
```

Set Zsh as Default Shell: To make Zsh your default shell, use the `chsh` command with the -s flag followed by the path to the Zsh executable. Run the following command:

```bash
chsh -s $(which zsh)
```

Confirm Default Shell Change: To confirm that Zsh is now your default shell, run the following command:

```bash
echo $SHELL
```

The output should be `/usr/bin/zsh`

**Install `oh-my-zsh`**

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

**Install PowerLevel10K**

```bash
git clone https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
```

Now that it’s installed, open the ~/.zshrc file with your preferred editor and change the value of ZSH_THEME as shown below:

```bash
ZSH_THEME="powerlevel10k/powerlevel10k"
```

To reflect this change on your terminal, restart it or run this command:

```bash
source ~/.zshrc
```

</details>

<details>
<summary>Terminal setup for Windows</summary>

**Follow these steps**

- Make sure you have `Windows terminal`.
- In terminal settings > Appearance > Turn on use acrylic material in tab row.
- Set schemes > [Windows terminal themes](https://windowsterminalthemes.dev/) > Select `Dracula` 
- Download FiraCode Nerd Fonts > [All font](https://github.com/ryanoasis/nerd-fonts/)
- Make sure you have `winget` in powershell. Install [Oh My Posh](https://ohmyposh.dev/docs/installation/windows)
- `winget install JanDeDobbeleer.OhMyPosh -s winget`
- Add path to Oh My Posh `$env:Path += ";C:\Users\user\AppData\Local\Programs\oh-my-posh\bin"`
- To update run `winget upgrade JanDeDobbeleer.OhMyPosh -s winget`
- To get themes `Get-PoshThemes`
- Run `oh-my-posh init pwsh --config 'C:\Users\zubae\AppData\Local\Programs\oh-my-posh\themes\easy-term.omp.json' | Invoke-Expression`
- To persist the powersell settings run `New-Item -Path $PROFILE -Type File -Force`
- Open powershell profile using `notepad $PROFILE`
- Add this line to the profile `oh-my-posh init pwsh --config 'C:\Users\zubae\AppData\Local\Programs\oh-my-posh\themes\easy-term.omp.json' | Invoke-Expression` save and exit. 
- Restart your terminal

</details>

## Vim Setup

**Pre Requisites**
- [Ripgrep](https://github.com/BurntSushi/ripgrep)
  ```sh
  brew install ripgrep
  ```

- [Node](https://nodejs.org/en/) and [Npm](https://nodejs.org/en/) - Recommended to install using nvm

**Neo Vim Configuration Rundown**

- Neo Vim configuration will be located in the home directory `~/.config/nvim`. 
- Uses `lua` for customizations
- Looks for `init.lua` file while Neo Vim starts

**Neo Vim Keymaps**

*General*
- `j` `k` - `INSET MODE`  To exit out of insert mode.

*Window Split*
- `space` `s` `v` - `CMD MODE` - To split window vertically.
- `space` `s` `h` - `CMD MODE` - To split window horizontally.
- `space` `s` `m` - `CMD MODE` - To maximize the selected window.
- `space` `s` `e` - `CMD MODE` - To reset windows evenly. after resizing the window manually.
- `space` `s` `x` - `CMD MODE` - To close the current active window.

*Tabs*
- `space` `t` `o` - `CMD MODE` - To open a new tab.
- `space` `t` `p` - `CMD MODE` - To got to previous tab.
- `space` `t` `n` - `CMD MODE` - To go to next tab.
- `space` `t` `x` - `CMD MODE` - To close the current tab.
- `space` `t` `f` - `CMD MODE` - To open existing file in a new tab.

*Telescope*
- `space` `e` `e` - `CMD MODE` - To open / close file explorer.
- `space` `e` `f` - `CMD MODE` - To open file explorer pointing current open window.
- `space` `e` `c` - `CMD MODE` - To collapse all open file / folders.
- `space` `e` `r` - `CMD MODE` - To reload file explorer.

*Fuzzy Find*
- `space` `f` `f` - `CMD MODE` - To open fuzzy find menu and search for files.
- `space` `f` `r` - `CMD MODE` - To search for recent files.
- `space` `f` `s` - `CMD MODE` - To find a string in files.
- `space` `f` `c` - `CMD MODE` - To the string under the cursor.
- `space` `f` `t` - `CMD MODE` - To find todo.

*Telescope Jumps*
- `ctrl` `o` - `CMD MODE` - To jump next window opened using telescope.
- `ctrl` `i` - `CMD MODE` - To jump previous window opened using telescope.

*Telescope Extended*
- `ctrl` `c` - `POPUP` - To close popup.
- `ctrl` `k` - `POPUP` - To select previous file.
- `ctrl` `j` - `POPUP` - To select next file.
- `ctrl` `q` - `POPUP` - To send selected files to quick fix.

*Sessions*
- `space` `w` `s` - `CMD MODE` - To save a session manually.
- `space` `w` `r` - `CMD MODE` - To restore a previously saved session.

*Block Jump*
- `ctrl` `space` - `CMD MODE` - To select the node.
- `ctrl` `backspace` - `CMD MODE` - To go back a selection.

*LSP*
- `ctrl` `j` - `CMD MODE` - To cycle next code completion suggestions.
- `ctrl` `k` - `CMD MODE` - To cycle back code completion suggestions.
- `ctrl` `b` - `CMD MODE` - To scroll down the docs.
- `ctrl` `f` - `CMD MODE` - To scroll up the docs.
- `ctrl` `e` - `CMD MODE` - To abort.
- `ctrl` `space` - `CMD MODE` - To open suggestions.

*Comments*
- `g` `c` - `CMD MODE` - Use this with conjunction to vim motions to comment / uncomment the sections. 

*Substitute*
- `s` - `CMD MODE` - To substitute yanked word with motion.
- `s` `s` - `CMD MODE` - To substitute yanked word to the line.
- `s` `S` - `CMD MODE` - To substitute yanked word to end of. the line.
- `x` `s` - `CMD MODE` - To substitute yanked word in visual mode.

*Word wrap*
- `y` `s` - `CMD MODE` - To start the surround functionality which can be used with motions.
- `c` `s` = `CMD MODE` - To change already surrounded word with different char.

*Git*
- `space` `h` `b` = `CMD MODE` - To view git blame.
- `space` `h` `b` = `CMD MODE` - To view git blame inline.

## Screenshots

<details>
<summary>Windows</summary>

![image](https://github.com/afrze/dev-environment/assets/86748499/ff0d7aff-bb0a-4ab2-81c6-1b23fc41a0be)

</details>

<details>
<summary>Mac</summary>

![image](https://github.com/afrze/dev-environment/assets/86748499/7cb3a07a-bf6a-44ad-8905-a0c044b31785)

</details>
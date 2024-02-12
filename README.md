# Development Environment Setup

This repository contains all the development environment setting, color themes, terminal setups, code editor setups etc.

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

- Everything is setup using [oh-my-posh](https://ohmyposh.dev/)
</details>

# Terminal setup for Windows

## To add new color schemes

Use [windows terminal themes](https://windowsterminalthemes.dev/), I use a theme called [purplepeter](/windows/purplepeter.json). Add this to your color schemes and select it. 

## Download and Install Fonts

I use [Fira Code](https://github.com/ryanoasis/nerd-fonts/releases), download an install it. And in windows terminal settings > appearance change to installed font.

## Install and setup Oh-My-Posh 

Make sure you have `winget`, if not install `winget`

Run this command to install `oh-my-posh`

```bash
winget install JanDeDobbeleer.OhMyPosh -s winget
```

To upgrade `Oh-My-Posh`

```bash
winget upgrade JanDeDobbeleer.OhMyPosh -s winget

```

To Activate, close and restart the windows terminal.

```bash
oh-my-posh init pwsh --config "$env:POSH_THEMES_PATH\capr4n.omp.json" | Invoke-Expression
```

If you get an error with ExecutionPolicy, like this

```bash
File C:\Users\zubae\AppData\Local\oh-my-posh\init.26.9.0.87be7bebafe4ef8e.10.ps1 cannot be loaded because running
scripts is disabled on this system. For more information, see about_Execution_Policies at
https:/go.microsoft.com/fwlink/?LinkID=135170.
At line:1 char:3
+ & 'C:\Users\zubae\AppData\Local\oh-my-posh\init.26.9.0.87be7bebafe4ef ...
+   ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : SecurityError: (:) [], PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess

```

Run this command, in a elevated terminal

```bash
Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned
```

To persists the theme applied, run these commands

```bash
notepad $PROFILE
```

In case of eny error, if `$PROFILE` does not exists, run this

```bash
New-Item -Path $PROFILE -Type File -Force
```

Inside the opened notepad file, paste this expression and save. 

```bash
oh-my-posh init pwsh --config "$env:POSH_THEMES_PATH\capr4n.omp.json" | Invoke-Expression
```
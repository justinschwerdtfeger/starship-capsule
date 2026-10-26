# Capsule — a Starship theme

## Installation

## Install FiraMono Nerd Font
https://www.nerdfonts.com/font-downloads
## Install Starship
https://starship.rs/guide/#%F0%9F%9A%80-installation
## System Specific Instructions
### Fish Setup
#### Setup Starship with Transient Prompt
Add this to ~/.config/fish/config.fish
```fish
function starship_transient_prompt_func
  starship module character
end
starship init fish | source
enable_transience
```
#### Install Theme
Clone this repository into .config
```fish
git clone https://github.com/justinschwerdtfeger/starship-capsule.git ~/.config/starship-capsule
```

Create a symbolic link (recommended):
```fish
ln -s ~/.config/starship-capsule/starship.toml ~/.config/starship.toml
```

Or copy the theme file into the .config directory:
```fish
cp ~/.config/starship-capsule/starship.toml ~/.config/starship.toml
```
### Windows Powershell Setup
#### Install Starship
Install Winget
```powershell
$progressPreference = 'silentlyContinue'
Write-Information "Downloading WinGet and its dependencies..."
Invoke-WebRequest -Uri https://aka.ms/getwinget -OutFile Microsoft.DesktopAppInstaller_8wekyb3d8bbwe.msixbundle
Invoke-WebRequest -Uri https://aka.ms/Microsoft.VCLibs.x64.14.00.Desktop.appx -OutFile Microsoft.VCLibs.x64.14.00.Desktop.appx
Invoke-WebRequest -Uri https://github.com/microsoft/microsoft-ui-xaml/releases/download/v2.7.3/Microsoft.UI.Xaml.2.7.x64.appx -OutFile Microsoft.UI.Xaml.2.7.x64.appx
Add-AppxPackage Microsoft.VCLibs.x64.14.00.Desktop.appx
Add-AppxPackage Microsoft.UI.Xaml.2.7.x64.appx
Add-AppxPackage Microsoft.DesktopAppInstaller_8wekyb3d8bbwe.msixbundle
```
Install Starship
```powershell
winget install Starship.Starship
```
#### Add Starship with Transient Prompt to $PROFILE
Create $PROFILE (if it does not already exist)
```powershell
New-Item -Path $PROFILE -Type File -Force
```

Open Profile with notepad
```powershell
notepad $PROFILE
```
Add this to $PROFILE and save
```
function Invoke-Starship-TransientFunction {
  &starship module character
}

Invoke-Expression (&starship init powershell)

Enable-TransientPrompt
```
Enable powershell script execution in Administrator Powershell
```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope LocalMachine
```
#### Install Theme
Install Git if it is not already installed
```powershell
winget install Git.Git
```
Clone this repository into AppData Local folder
```powershell
git clone https://github.com/justinschwerdtfeger/starship-capsule.git $env:LOCALAPPDATA/starship-capsule
```
Create a .config directory (if it does not already exist)
```powershell
New-Item -ItemType Directory -Force ~/.config
```
Copy the theme file into the .config directory
```powershell
cp $env:LOCALAPPDATA/starship-capsule/starship.toml ~/.config
```

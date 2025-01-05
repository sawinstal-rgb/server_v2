# Installing Git for Checkpoints

Cline uses Git under the hood to create checkpoints of your workspace throughout tasks. Every time Cline makes changes to your files, it automatically creates a Git commit, allowing you to track and revert changes if needed. Follow the instructions below to install Git for your operating system.

## Windows

1. Download the official Git installer from [git-scm.com](https://git-scm.com/download/windows)
2. Run the installer you downloaded (e.g., `Git-2.X.X-64-bit.exe`)
3. During installation:
   - Accept the default settings unless you have specific preferences
   - For "Adjusting your PATH environment", select "Git from the command line and also from 3rd-party software"
   - For terminal emulator, choose "Use Windows' default console window"
4. Click through the rest of the installer using the default settings

## macOS

### Option 1: Using the Official Installer

1. Download the latest Git installer from [git-scm.com](https://git-scm.com/download/mac)
2. Double click the downloaded package (e.g., `git-2.X.X-intel-universal-mavericks.dmg`)
3. Follow the installation prompts

### Option 2: Using Homebrew

1. If you don't have Homebrew installed, [install it first](https://brew.sh)
2. Install Git using Homebrew:
   ```bash
   brew install git
   ```

## Linux

### Ubuntu/Debian

1. Open Terminal and update your package index:
   ```bash
   sudo apt update
   ```
2. Install Git:
   ```bash
   sudo apt install git
   ```

## After Installation

After following the installation process, restart VS Code. Cline will automatically detect Git and enable checkpoints.
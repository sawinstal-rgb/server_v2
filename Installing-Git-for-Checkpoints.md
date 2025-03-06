# Installing Git for Checkpoints

Cline uses Git under the hood to create checkpoints of your workspace throughout tasks. Every time Cline makes changes to your files, it automatically creates a Git commit, allowing you to track and revert changes if needed. Follow the instructions below to install Git for your operating system.

## macOS

1. If you don't have Homebrew installed, [install it first](https://brew.sh)
2. Install Git using Homebrew:
   ```bash
   brew install git
   ```
3. Quit and re-open VSCode. Cline will automatically detect Git and enable checkpoints.

## Windows

1. Download and run the official Git installer from [git-scm.com](https://git-scm.com/downloads/win)
2. Quit and re-open VSCode. Cline will automatically detect Git and enable checkpoints.

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
3. Quit and re-open VSCode. Cline will automatically detect Git and enable checkpoints.

## Support

If you've followed these steps and are still experiencing problems, please:

1. Check the [Cline GitHub Issues](https://github.com/cline/cline/issues) to see if others have reported similar problems
2. If not, create a new issue with details about your operating system, VSCode/Cursor version, and the steps you've tried

For additional help, join our [Discord](https://discord.gg/cline).
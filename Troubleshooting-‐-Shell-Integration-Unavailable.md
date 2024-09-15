- [What is Shell Integration?](#what-is-shell-integration)
- [How to Fix "Shell Integration Unavailable"](#how-to-fix-shell-integration-unavailable)
  - [Step 1: Update VSCode or Cursor](#step-1-update-vscode-or-cursor)
  - [Step 2: Configure VSCode to Use the Correct Shell](#step-3-configure-vscode-to-use-the-correct-shell)
  - [Step 3: Restart VSCode](#step-4-restart-vscode)
- [Still Having Trouble?](#still-having-trouble)
- [Unusual Terminal Output](#unusual-terminal-output)
- [Support](#support)

## What is Shell Integration?

Shell integration is a [new feature in VSCode 1.93](https://code.visualstudio.com/updates/v1_93#_terminal-shell-integration-api) that allows extensions like Claude Dev to run commands in your terminal and read their output. Command output allows Claude to react to the result of the command on his own, without you having to handhold by copy-pasting the output in yourself. It's also quite powerful when running development servers as it allows Claude to fix errors as the server logs them.

## How to Fix "Shell Integration Unavailable"

### Step 1: Update VSCode or Cursor

First, make sure you're using the latest version of VSCode or Cursor:

1. Open VSCode or Cursor
2. Press `Cmd + Shift + P` (Mac) or `Ctrl + Shift + P` (Windows/Linux)
3. Type "Check for Updates" (VSCode) or "Attempt Update" (Cursor) and select it
4. Restart VSCode/Cursor after the update

### Step 2: Configure VSCode to Use the Correct Shell

1. Open VSCode
2. Press `Cmd + Shift + P` (Mac) or `Ctrl + Shift + P` (Windows/Linux)
3. Type "Terminal: Select Default Profile" and choose it
4. Select one of the supported shells: zsh, bash, fish, or PowerShell.

### Step 4: Restart VSCode

After making these changes:

1. Quit VSCode completely
2. Reopen VSCode
3. Start a new Claude Dev session (you can resume your previous task and try to run the command again, this time with Claude being able to see the output)

## Still Having Trouble?

If you're still experiencing issues after trying the basic troubleshooting steps, you can try [manually installing shell integration](https://code.visualstudio.com/docs/terminal/shell-integration#_manual-installation). 

For example, if you use zsh:

1. Run `code ~/.zshrc` in the terminal to open your zsh configuration file.
2. Add the following line to your `~/.zshrc`:

```bash
[[ "$TERM_PROGRAM" == "vscode" ]] && . "$(code --locate-shell-integration-path zsh)"
```

3. Save the file.
4. Quit VSCode completely.
5. Reopen VSCode and start a new Claude Dev session.

If you use PowerShell you would do:
1. Run `code $Profile` in the terminal to open your PowerShell profile.
2. Add the following line to the file:

```bash
if ($env:TERM_PROGRAM -eq "vscode") { . "$(code --locate-shell-integration-path pwsh)" }
```

## Unusual Terminal Output

If you're seeing unusual output with rectangles, lines, escape sequences, or control characters, it may be related to terminal customization tools. Common culprits include:

- Powerlevel10k: A zsh theme that adds visual elements to the prompt
- Oh My Zsh: A framework for managing zsh configurations
- Fish shell themes

To troubleshoot:

1. Temporarily disable these tools in your shell configuration file (e.g., `~/.zshrc` for Zsh)
2. If the issue resolves, gradually re-enable features to identify the conflicting component

For example, if you're using Powerlevel10k with Zsh, you can disable it by commenting out the relevant line in your `~/.zshrc` file:

```bash
# Comment out the Powerlevel10k source line
# source /path/to/powerlevel10k/powerlevel10k.zsh-theme
```

If disabling these customizations resolves the issue, you may need to find alternative configurations that are compatible with VSCode's shell integration feature.

## Support

If you've followed these steps and are still experiencing problems, please:

1. Check the [Claude Dev GitHub Issues](https://github.com/saoudrizwan/claude-dev/issues) to see if others have reported similar problems
2. If not, create a new issue with details about your operating system, VSCode/Cursor version, and the steps you've tried

For additional help, join our [Discord](https://discord.gg/claudedev).
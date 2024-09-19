- [How to Fix "powershell is not recognized"](#how-to-fix-powershell-is-not-recognized)
- [Additional Troubleshooting](#additional-troubleshooting)
- [Support](#support)

If you're seeing an error message like this:

```
Command failed with exit code 1: powershell (Get-CimInstance -ClassName Win32_OperatingSystem).caption
'powershell' is not recognized as an internal or external command,
operable program or batch file.
```

This usually means that Windows can't find the PowerShell executable. This is typically caused by the user (or system) PATH environment variable not containing the directory where the PowerShell executable resides.

## How to Fix "'powershell' is not recognized"

1. Press `Windows + X` (or right-click on the Start button) and select "System". On the left side, click "Advanced system settings".
2. In the System Properties window, click the "Environment Variables" button near the bottom.  
3. In the Environment Variables window, under "System variables" or "User variables" (depending on whether you want to make the change globally or for just your user), find the variable named "Path" and click "Edit".  
4. In the Edit Environment Variable window, click "New", then paste the following:
   ```
   %SYSTEMROOT%\System32\WindowsPowerShell\v1.0\
   ```  
5. Click "OK" on all windows to save your changes.  
6. Restart your computer for the changes to take effect.

![image](https://github.com/user-attachments/assets/a0e2ec9b-d9f8-4b9d-b7c5-758960e68eaa)

## Additional Troubleshooting

If you're still experiencing issues after trying these solutions:

1. Verify PowerShell Installation:
   - Open File Explorer and navigate to `C:\Windows\System32\WindowsPowerShell\v1.0\`
   - Check if `powershell.exe` exists in this folder

2. Check System PATH:
   - Open Command Prompt and type `echo %PATH%`
   - Verify that the PowerShell directory is listed

3. Sometimes, a system restart is needed for environment variable changes to take effect

## Support

If you've followed these steps and are still experiencing problems, please:

1. Check the [Claude Dev GitHub Issues](https://github.com/saoudrizwan/claude-dev/issues) to see if others have reported similar problems
2. If not, create a new issue with details about your operating system, VSCode/Cursor version, and the steps you've tried

For additional help, join our [Discord](https://discord.gg/claudedev).
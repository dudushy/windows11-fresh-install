# windows11-fresh-install
A step-by-step guide on how to setup/debloat Windows 11
## While setting up Windows 11
- Press `SHIFT` + `F10` to open the CMD Terminal, then run:
  ```
  oobe\bypassnro
  ```
## After Windows 11 setup
- [Lenovo laptop ABNT keyboard layout fix](https://support.lenovo.com/br/pt/solutions/ht509895-how-to-enable-key-lenovo-100e300e)
- Open the Terminal and run:
  ```ps
  irm https://christitus.com/win | iex
  ```
  > Check the Tweaks, Features and Settings that you want (install WSL later)
- Install the applications you need via Winget with this awesome [site](https://winget.run/)
  > Heres a sample of my personal apps
  ```txt
  winget install 9NKSQGP7F2NH --source msstore --silent --accept-package-agreements --accept-source-agreements --disable-interactivity; winget install Spotify.Spotify Discord.Discord Brave.Brave Bitwarden.Bitwarden VideoLAN.VLC WinSCP.WinSCP Famatech.AdvancedIPScanner RaspberryPiFoundation.RaspberryPiImager SublimeHQ.SublimeText.4 GitExtensionsTeam.GitExtensions CPUID.CPU-Z RARLab.WinRAR Valve.Steam Klocman.BulkCrapUninstaller qBittorrent.qBittorrent AnyDeskSoftwareGmbH.AnyDesk Microsoft.PowerShell Microsoft.PowerToys Nvidia.GeForceExperience Microsoft.WindowsTerminal Microsoft.VisualStudioCode Notion.Notion Google.GoogleDrive GitHub.Copilot Git.Git --source winget --exact --silent --accept-package-agreements --accept-source-agreements --disable-interactivity
  ```
- Download and install Excel, PowerPoint and Word
  1. Go to the Windows installation disk and create a folder named `Office` (like `C:/Office`)
  2. Copy the `Configuration.xml` file to the folder from the [sample](./samples/Configuration.xml) or [create your own](https://config.office.com/deploymentsettings)
  3. Download the `setup.exe` to the folder from the [link](https://officecdn.microsoft.com/pr/wsus/setup.exe)
  4. Open the CMD as **Administrator** and run:
    ```cmd
    cd /d C:\Office\
    setup.exe /configure Configuration.xml
    ```
- Activate Windows and Office
  ```ps
  irm https://get.activated.win | iex
  ```
## Install WSL 2 and Ubuntu
1. Open PowerShell as Administrator.
2. Install WSL without a Linux distribution:
   ```powershell
   wsl --install --no-distribution
   ```
3. Restart Windows:
   ```powershell
   Restart-Computer
   ```
4. After restarting, open PowerShell as Administrator and update WSL:
   ```powershell
   wsl --update
   ```
   If the Microsoft Store installation fails, use:
   ```powershell
   wsl --update --web-download
   ```
5. Set WSL 2 as the default version:
   ```powershell
   wsl --set-default-version 2
   ```
6. Check the available Linux distributions:
   ```powershell
   wsl --list --online
   ```
7. Install Ubuntu:
   ```powershell
   wsl --install -d Ubuntu
   ```
   If the Microsoft Store installation fails, use:
   ```powershell
   wsl --install -d Ubuntu --web-download
   ```
8. During the first Ubuntu launch, create your Linux username and password.
9. Update Ubuntu:
   ```bash
   sudo apt update && sudo apt upgrade -y
   ```
10. Confirm that Ubuntu is using WSL 2:
    ```powershell
    wsl --list --verbose
    ```
11. Check the WSL status and version:
    ```powershell
    wsl --status
    wsl --version
    ```
## Bonus: Setup OH-MY-ZSH on WSL
- Follow [this guide](https://github.com/dudushy/install-oh-my-zsh)
## References:
- https://github.com/christitustech/winutil
- https://winget.run/
- https://massgrave.dev/

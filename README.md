# windows11-fresh-install
A step-by-step guide on how to setup/debloat Windows 11
## While setting up Windows 11
- Press `SHIFT` + `F10` to open the CMD Terminal, then run:
  ```
  oobe\bypassnro
  ```
## After Windows 11 setup
- Open the Terminal and run:
  ```ps
  irm https://christitus.com/win | iex
  ```
  > Check the Tweaks, Features and Settings that you want
- Install the applications you need via Winget with this awesome [site](https://winget.run/)
  > Heres a sample of my personal apps
  ```txt
  winget install 9NKSQGP7F2NH Spotify.Spotify Discord.Discord Brave.Brave Bitwarden.Bitwarden VideoLAN.VLC WinSCP.WinSCP Famatech.AdvancedIPScanner RaspberryPiFoundation.RaspberryPiImager SublimeHQ.SublimeText.4 GitExtensionsTeam.GitExtensions CPUID.CPU-Z RARLab.WinRAR Valve.Steam Klocman.BulkCrapUninstaller qBittorrent.qBittorrent AnyDeskSoftwareGmbH.AnyDesk Microsoft.PowerShell Canonical.Ubuntu.2204 Microsoft.PowerToys Nvidia.GeForceExperience Microsoft.WindowsTerminal Microsoft.VisualStudioCode Notion.Notion Google.GoogleDrive --silent --accept-package-agreements --accept-source-agreements --disable-interactivity
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
## Lenovo laptop ABNT keyboard layout fix
- https://support.lenovo.com/br/pt/solutions/ht509895-how-to-enable-key-lenovo-100e300e
## Bonus: Setup OH-MY-ZSH on WSL
- Follow [this guide](https://github.com/dudushy/install-oh-my-zsh)
## References:
- https://github.com/christitustech/winutil
- https://winget.run/
- https://massgrave.dev/

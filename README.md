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
  winget install -e --id WhatsApp.WhatsApp;winget install -e --id Spotify.Spotify;winget install -e --id Discord.Discord;winget install -e --id Brave.Brave;winget install -e --id Bitwarden.Bitwarden;winget install -e --id VideoLAN.VLC;winget install -e --id WinSCP.WinSCP;winget install -e --id Famatech.AdvancedIPScanner;winget install -e --id RaspberryPiFoundation.RaspberryPiImager;winget install -e --id SublimeHQ.SublimeText.4;winget install -e --id GitExtensionsTeam.GitExtensions;winget install -e --id CPUID.CPU-Z;winget install -e --id RARLab.WinRAR;winget install -e --id Valve.Steam;winget install -e --id Klocman.BulkCrapUninstaller;winget install -e --id qBittorrent.qBittorrent;winget install -e --id AnyDeskSoftwareGmbH.AnyDesk;winget install -e --id Microsoft.PowerShell;winget install -e --id Canonical.Ubuntu.2204;winget install -e --id Microsoft.PowerToys;winget install -e --id Nvidia.GeForceExperience;winget install -e --id Microsoft.WindowsTerminal;winget install -e --id Microsoft.VisualStudioCode;winget install -e --id Notion.Notion;winget install -e --id Google.Drive
  ```
- Download and install Excel, PowerPoint and Word
  1. Go to the Windows installation disk and create a folder named `Office` (like `C:/Office`)
  2. Copy the `Configuration.xml` file to the folder from the [sample]() or [create your own](https://config.office.com/deploymentsettings)
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
## Bonus: Setup OH-MY-ZSH on WSL
- Follow [this guide]()
## References:
- https://github.com/christitustech/winutil
- https://winget.run/
- https://massgrave.dev/

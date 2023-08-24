# My windows setup

## Installation
Start the windows installer and make sure the locale is set to `English (World)`


## TPM/Secure Boot bypass
<details>
  <summary><i>If your machine does not have a TPM module and/or has Secure Boot disabled</i></summary>
    
    Open CMD with Shift + F10 and enter `regedit`

    Create `LabConfig` key under `HKEY_LOCAL_MACHINE\SYSTEM\Setup`

    Create the following DWORD entries under the LabConfig key:
        - BypassTPMCheck
        - BypassSecureBootCheck

    Both entries should have the value of `1`

</details>


## OOBE
When OOBE opens, wait for the region settings to time out with a <b>OOBEREGION</b> error, and click <b>skip</b>

Go through the rest of OOBE normally 


## Post OOBE
Open settings and head to "Windows Update"

Click on "Check for updates", install available updates and reboot 

Repeat previous step until on updates appear when clicking "Check for updates"


## Debloat windows
Open powershell as Administrator and enter `iwr -useb https://christitus.com/win | iex` to start CTT's utility

Press "n" when prompted

Under the "Install" tab, select the programs you want installed and press "Install selection"

Under the "Tweaks" tab, select the desktop preset, make sure all the checkboxes on the left is clicked

Make sure dark theme is on, bing search is off, ultimate performace profile is added and a WinUtil shortcut is added to your desktop

On the right side, check "Disable Power Throttling", "Show File Extentions", "Remove Cortana", "Remove Microsoft Edge", "Set Classic Right-Click Menu", "Disable Mouse Acceleration", "Enable Verbose Logon Messages" and "Cloudflare" in the DNS dropdown

Click "Run Tweaks" and reboot your computer when tweaks are finished


## Windows activation
<details>
  <summary><i>If your machine does not have an active windows key</i></summary>

    Open powershell as Administrator and enter `irm https://massgrave.dev/get | iex` to start massgravel's windows activation script
    
    Select HWID by pressing `1` when prompted for an activation method

    When the program has returned to the initial screen, press `0` to exit the program

</details>


## Disable startup programs
Hold, Control, Shift and press Ecscape at the same time. This will cause task manager to launch

Enter the "Startup apps" tab and disable all unwanted startup apps


## Windows Settings
Enter the Settings app and change following settings

- System
    - Power
        - Power Mode: Best Performance
    - Multitasking
        - Snap windows: True
            - When i snap a windows, suggest...: False
            - Show snap layouts when i hover...: False
            - Show snap layouts when i drag...: False
            - Show my snapped windows when...: False
            - When i drag a window, let me...: True
- Personalization
    - Colors
        - Transperency effects: False
        - Accent color
            - Color: The color of your choise
            - Show accent color on Start and taskbar: True
            - Show accent color on title bars and windows borders: True
    - Start
        - Layout: More pins
        - Show recently added apps: False
        - Show most used apps: False
        - Show recently opened items...: False
        - Show reccomendations for...: False
    - Taskbar
        - Taskbar items
            - Search: Search icon only
            - Task view: False
            - Widgets: False
            - Chat: False
- Apps
    - Installed Apps: Remove all unused microsoft bloatware
    - Default Apps: Make sure your browser is set as the default browser
- Time & language
    - Time zone: Set as your time zone
- Gaming
    - Xbox Game Bar
        - Open Xbox Game Bar...: False
    - Game Mode
        - Game Mode: False
- Accessibility
    - Visual Effects
        - Animation effects: False
- Privacy & security
    - For developers
        - Developer Mode: True
        - Remove Desktop
            - Remote Desktop: True
                - Require devices to use NLA: False
    - Terminal: Windows Terminal
    - PowerShell
        - Change execution policy to allow local...: True

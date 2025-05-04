# Uninstallation-Guide.-Md

# Uninstallation Guide

**Version**: 1.0  
**Date**: May 04, 2025  
**Purpose**: To provide instructions for uninstalling programs and browser extensions, with third-party tools HiBit Uninstaller and Microsoft Office uninstallation methods, on Windows, macOS, and Linux systems.

---

## Table of Contents

- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [Uninstallation Instructions](#uninstallation-instructions)
  - [General Programs](#general-programs)
  - [Browser Extensions](#browser-extensions)
  - [HiBit Uninstaller (Third-Party Tool, Windows)](#hibit-uninstaller-third-party-tool-windows)
  - [Microsoft Office (Third-Party Tool Assisted, Windows, macOS)](#microsoft-office-third-party-tool-assisted-windows-macos)
- [Post-Uninstallation Checks](#post-uninstallation-checks)
- [Troubleshooting](#troubleshooting)
- [Additional Notes](#additional-notes)
- [Contributing](#contributing)
- [Support](#support)

---

## Introduction

This guide provides step-by-step instructions for uninstalling programs and browser extensions from your system, ensuring a clean removal of associated files and settings. It includes general procedures for Windows, macOS, and Linux, alongside specific instructions for using **HiBit Uninstaller** and **Microsoft Office** uninstallation tools as third-party solutions. HiBit Uninstaller is a free Windows utility for removing software, Windows Store apps, and browser extensions, while Microsoft Office uninstallation leverages Microsoft’s tools, with optional HiBit cleanup for residuals.

---

## Prerequisites

- Administrative or `sudo` privileges (where required).
- Backup of critical data (e.g., program settings, Office documents, browser bookmarks).
- Access to the system where the software or extensions are installed.
- For HiBit Uninstaller: Download from [HiBitSoft](https://www.hibitsoft.ir) (installed or portable version, version 3.2.55 as of February 2025).
- For Microsoft Office: Optional access to the [Microsoft Support and Recovery Assistant](https://support.microsoft.com/en-us/office/uninstall-office-from-a-pc-9dd49b83-264a-477a-8fcc-2fdf5dbf61d8).

---

## Uninstallation Instructions

### General Programs

#### Windows

1. **Close the Program**:
   - Ensure the program is not running. Use Task Manager (`Ctrl + Shift + Esc`) to terminate related processes.

2. **Uninstall via Control Panel**:
   - Open **Control Panel** (`Windows + R`, type `control`, press `Enter`).
   - Navigate to **Programs > Programs and Features**.
   - Locate the program, right-click, and select **Uninstall**.
   - Follow the uninstallation wizard prompts.

3. **Remove Residual Files**:
   - Navigate to:
     - `C:\Program Files` or `C:\Program Files (x86)` for the program folder.
     - `C:\Users\<YourUsername>\AppData\Local` or `Roaming` for user-specific data.
   - Delete program-related folders.
   - (Optional) Use `regedit` to remove registry entries in `HKEY_LOCAL_MACHINE\SOFTWARE` or `HKEY_CURRENT_USER\SOFTWARE` (back up the registry first).

4. **Restart**:
   - Reboot the system to apply changes.

#### macOS

1. **Quit the Program**:
   - Ensure the program is not running. Use **Force Quit** (`Command + Option + Esc`) if needed.

2. **Remove the Application**:
   - Open **Finder** and navigate to the **Applications** folder.
   - Drag the program’s `.app` file to the **Trash** or right-click and select **Move to Trash**.

3. **Delete Associated Files**:
   - Open **Finder**, press `Command + Shift + G`, and check:
     - `~/Library/Application Support/<ProgramName>`
     - `~/Library/Preferences/<ProgramName>.plist`
     - `~/Library/Caches/<ProgramName>`
   - Move related files to the **Trash** and empty it.

4. **Restart**:
   - Reboot the Mac to finalize.

#### Linux (Ubuntu-based)

1. **Identify the Package**:
   - Open a terminal (`Ctrl + Alt + T`).
   - Run `dpkg -l | grep <program-name>` to find the package name.

2. **Uninstall the Program**:
   - Run:
     ```bash
     sudo apt remove <package-name>
     sudo apt purge <package-name>
     sudo apt autoremove
     ```

3. **Remove Residual Files**:
   - Check for user-specific configuration files:
     ```bash
     rm -rf ~/.local/share/<program-name>
     rm -rf ~/.config/<program-name>
     ```

4. **Update Package Cache**:
   - Run:
     ```bash
     sudo apt update
     ```

5. **Restart**:
   - Reboot the system:
     ```bash
     sudo reboot
     ```

### Browser Extensions

Browser extensions (interpreted as “control keys”) are managed through the browser’s settings. Below are steps for common browsers.

#### Google Chrome

1. Open Chrome and click the **three-dot menu** > **Extensions** > **Manage Extensions**.
2. Locate the extension, click **Remove**, and confirm.
3. (Optional) Clear residual data:
   - Navigate to:
     - Windows: `C:\Users\<YourUsername>\AppData\Local\Google\Chrome\User Data\Default\Extensions`
     - macOS: `~/Library/Application Support/Google/Chrome/Default/Extensions`
     - Linux: `~/.config/google-chrome/Default/Extensions`
   - Delete the extension’s folder (identified by its ID).

#### Mozilla Firefox

1. Open Firefox and click the **menu** > **Add-ons and Themes** > **Extensions**.
2. Locate the extension, click **Remove**, and confirm.
3. (Optional) Clear residual data:
   - Navigate to:
     - Windows: `C:\Users\<YourUsername>\AppData\Roaming\Mozilla\Firefox\Profiles\<profile>\extensions`
     - macOS: `~/Library/Application Support/Firefox/Profiles/<profile>/extensions`
     - Linux: `~/.mozilla/firefox/<profile>/extensions`
   - Delete the extension’s folder.

#### Microsoft Edge

1. Open Edge and click the **three-dot menu** > **Extensions** > **Manage Extensions**.
2. Locate the extension, click **Remove**, and confirm.
3. (Optional) Clear residual data:
   - Navigate to:
     - Windows: `C:\Users\<YourUsername>\AppData\Local\Microsoft\Edge\User Data\Default\Extensions`
     - macOS: `~/Library/Application Support/Microsoft Edge/Default/Extensions`
     - Linux: `~/.config/microsoft-edge/Default/Extensions`
   - Delete the extension’s folder.

### HiBit Uninstaller (Third-Party Tool, Windows)

HiBit Uninstaller is a free Windows utility (version 3.2.55 as of February 2025) for uninstalling programs, Windows Store apps, and browser extensions, with tools to clean residual files and registry entries. It supports installed and portable modes.

1. **Uninstall Programs with HiBit Uninstaller**:
   - Download and run HiBit Uninstaller from [HiBitSoft](https://www.hibitsoft.ir).
   - In the **Uninstaller** tab, locate the program in the list.
   - Click **Uninstall** and follow the prompts.
   - After uninstallation, select **Powerful Scan** to detect and delete residual files and registry entries (e.g., in `C:\Program Files` or `HKEY_LOCAL_MACHINE\SOFTWARE`).

2. **Uninstall Browser Extensions with HiBit Uninstaller**:
   - Open the **Tools** menu > **Browsers**.
   - Select your browser (e.g., Chrome, Firefox, Edge).
   - Locate the extension, check it, and click **Delete**.
   - Run **Powerful Scan** to remove residual extension data.

3. **Uninstall HiBit Uninstaller Itself**:
   - **Installed Version**:
     - Open **Control Panel** > **Programs > Programs and Features**.
     - Locate **HiBit Uninstaller**, right-click, and select **Uninstall**.
   - **Portable Version**:
     - Delete the folder where HiBit Uninstaller was extracted (e.g., `C:\Users\<YourUsername>\Downloads\HiBitUninstallerPortable`).
   - **Residual Files**:
     - Navigate to:
       - `C:\Users\<YourUsername>\AppData\Local\HiBitUninstaller`
       - `C:\Program Files\HiBitUninstaller` (installed version)
     - Delete any HiBit-related folders.
     - Use HiBit’s **Junk Files Cleaner** or **Registry Cleaner** before uninstalling to remove its own residuals.

4. **Restart**:
   - Reboot the system to apply changes.

### Microsoft Office (Third-Party Tool Assisted, Windows, macOS)

Microsoft Office (e.g., Office 365, 2019, 2021, 2024) can be uninstalled using Microsoft’s tools, with HiBit Uninstaller for residual cleanup on Windows.

#### Windows

1. **Close Office Applications**:
   - Ensure all Office apps (e.g., Word, Excel, Outlook) are closed. Use Task Manager (`Ctrl + Shift + Esc`) to terminate processes like `WINWORD.EXE` or `EXCEL.EXE`.

2. **Use Microsoft Support and Recovery Assistant (Primary Method)**:
   - Download from [Microsoft Support](https://support.microsoft.com/en-us/office/uninstall-office-from-a-pc-9dd49b83-264a-477a-8fcc-2fdf5dbf61d8):
     - Under **Option 2 (Click-to-Run or MSI)**, click **Download** to get `SetupProd_OffScrub.exe`.
   - Run the tool, select the Office version to uninstall, and follow the prompts.
   - Command-line alternative (elevated Command Prompt):
     ```bash
     SaRAcmd.exe -S OfficeScrubScenario -AcceptEula -OfficeVersion All
     ```
   - Note: The tool may not support Office 2024. Use manual methods if needed.

3. **Manual Uninstallation (Alternative)**:
   - Open **Control Panel** > **Programs > Programs and Features**.
   - Locate **Microsoft Office** (e.g., Microsoft 365, Office 2021), right-click, and select **Uninstall**.
   - Alternatively, use **Settings** > **Apps > Installed Apps**, find Office, and select **Uninstall**.

4. **Clean Residuals with HiBit Uninstaller**:
   - Open HiBit Uninstaller.
   - In the **Uninstaller** tab, locate Microsoft Office (if still listed) and uninstall.
   - Run **Powerful Scan** to delete residual files in:
     - `C:\Program Files\Microsoft Office`
     - `C:\Program Files (x86)\Microsoft Office`
     - `C:\Users\<YourUsername>\AppData\Local\Microsoft\Office`
   - Use the **Registry Cleaner** to remove Office-related registry entries in `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft`.

5. **Restart**:
   - Reboot the system.

#### macOS

1. **Quit Office Applications**:
   - Ensure all Office apps are closed. Use **Force Quit** (`Command + Option + Esc`) if needed.

2. **Remove Office Applications**:
   - Open **Finder** > **Applications**.
   - Drag **Microsoft Word**, **Excel**, **Outlook**, etc., to the **Trash** or right-click and select **Move to Trash**.

3. **Delete Associated Files**:
   - Press `Command + Shift + G` in **Finder** and check:
     - `~/Library/Application Support/Microsoft`
     - `~/Library/Preferences/com.microsoft.*.plist`
     - `~/Library/Caches/com.microsoft.*`
   - Move related files to the **Trash** and empty it.
   - Note: HiBit Uninstaller is Windows-only. Use [AppCleaner](https://freemacsoft.net/appcleaner/) for macOS residual cleanup.

4. **Restart**:
   - Reboot the Mac.

---

## Post-Uninstallation Checks

- **Verify Removal**:
   - Search for the program or extension in the Start menu, Applications folder, or browser settings.
   - Check for running processes:
     - Windows: `tasklist | findstr <program-name>`
     - macOS/Linux: `ps aux | grep <program-name>`
- **Check Disk Space**:
   - Use **Disk Cleanup** (Windows), **Storage Management** (macOS), or `du -sh ~` (Linux).
- **Test System Stability**:
   - Monitor for errors or performance issues post-uninstallation.

---

## Troubleshooting

- **HiBit Uninstaller**: Fails to uninstall a program or itself.
   - Use the **Force Uninstall** feature for stubborn programs.
   - Manually delete HiBit’s folder and registry entries via `regedit` in `HKEY_LOCAL_MACHINE\SOFTWARE\HiBitUninstaller` (back up the registry).
   - Re-download from [HiBitSoft](https://www.hibit acumsoft.ir) if issues persist.
- **Microsoft Office**: Tool fails to uninstall.
   - Use the [Microsoft Program Install and Uninstall Troubleshooter](https://support.microsoft.com/en-us/topic/fix-problems-that-block-programs-from-being-installed-or-removed-cca7d1b6-65a9-3d98-8394-688972fd8ba9).
   - Run HiBit Uninstaller’s **Powerful Scan** to remove stuck residuals.
- **Browser Extensions**: Fail to remove.
   - Reset the browser to factory settings via its settings menu.
   - Use HiBit Uninstaller’s **Browsers** tool to force removal on Windows.

---

## Additional Notes

- **Backup**: Save critical data (e.g., Office documents, browser bookmarks) before uninstalling. Uninstalling does not delete user-created files.
- **Third-Party Tools**: HiBit Uninstaller is ideal for Windows cleanup. For macOS, use [AppCleaner](https://freemacsoft.net/appcleaner/). Other tools include [CCleaner](https://www.ccleaner.com) or [Revo Uninstaller](https://www.revouninstaller.com).
- **Vendor Instructions**: Refer to [HiBit Uninstaller](https://www.hibitsoft.ir) or [Microsoft Support](https://support.microsoft.com) for specific guidance.

---

## Contributing

Contributions to improve this guide are welcome! To contribute:
1. Fork the repository.
2. Create a new branch:
   ```bash
   git checkout -b improve-uninstall-guide

# Windows 11 Installation Bloatware Remover

<br>Welcome to the Windows 11 installation bloatware remover. This guide automates the process of installing and setting up a clean copy of Windows 11, including downloading the latest version, creating a bootable pen drive, running the decrapifier script to remove bloatware, and installing necessary drivers.<br/>

# 📋 Prerequisites
💻 Download the latest version of Windows 11 and create a bootable pen drive using the media creation tool: https://www.microsoft.com/software-download/windows11
<br>🔌 Ensure that your BIOS is set up in UEFI mode and legacy compatibility modes are disabled. Safe boot can also be enabled.
<br>📀 Download the latest AMD and Nvidia drivers and any other necessary motherboard drivers.
<br>📂 Create a decrapifier.ps1 file using the script at https://community.spiceworks.com/scripts/show/4378-windows-10-decrapifier-18xx-19xx-2xxx and copy it to your bootable pen drive.

# <br>🚀 Installation instructions
🗂️ Insert the bootable pen drive and boot into the Windows 11 installer.
<br>💾 Once loaded, select Windows 11 Pro and choose custom install to get to the storage list, but do not proceed further.
<br>💻 Press Shift + F10 to open a CMD window.
<br>📜 Type diskpart and press enter.
<br>💾 Type list disk to list the available drives.
<br>📜 Type select disk X where X is the number of the drive you want to use.
<br>💾 Type clean to erase the entire drive.
<br>📜 Type convert gpt to convert the drive from MBR to GPT partitioning.
<br>📜 : Enter the following commands in order
<br>create partition efi size=100
<br>format quick fs=fat32 label="System"
<br>assign letter="S"
<br>create partition msr size=16
<br>create partition primary size=122976
<br>format quick fs=ntfs label="Windows"
<br>assign letter="C"
<br>💻 Close the CMD window and refresh the storage page in the GUI (you may need to cancel and go back to the beginning of the installer if it complains about the C drive).
<br>💾 Choose the Windows partition you created and click Next to install Windows 11.
<br>🖥️ Once installed and at the desktop for the first time, go to the Start Menu and type Powershell. Right click on Powershell and select "Run as Administrator".
<br>📜 Enter the following into Powershell: Set-ExecutionPolicy Unrestricted. Press a and enter to confirm.
<br>🗂️ Plug in your USB pen drive if it was removed, and navigate to the drive letter in Powershell (e.g. cd X:\).
<br>📂 If the decrapifier.ps1 file is on the root of the pen drive, type .\decrapifier.ps1 and press the Tab key to auto-complete the line. If it is not on the root, add the folder names to the path (or move the file to the root for convenience)
<br>📂Add the following to the end of the line before pressing enter: -ClearStart -Xbox -OneDrive.
<br>📜Press enter and let the script run.

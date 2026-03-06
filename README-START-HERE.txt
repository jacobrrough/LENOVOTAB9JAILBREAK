================================================================================
SMOOTHEST GSI - ALL-IN-ONE (LineageOS 18.1 + GApps + tweaks)
================================================================================

I've set everything up. One thing can't be automated: SourceForge blocks
scripted downloads, so you have to download the GSI file once in your browser.

STEP 1 - Download the GSI (one time, in browser)
-----------------------------------------------
1. Open this page (or run DO-IT-ALL.ps1 once - it will open it for you):
   https://sourceforge.net/projects/andyyan-gsi/files/lineage-18.x/

2. Download the file: lineage-18.1-20240121-UNOFFICIAL-arm64_bgN.img.xz
   (About 600 MB. If the date is different, pick the newest "arm64_bgN" .img.xz)

3. Save it to this folder: C:\Users\jrrou\tablet-gsi\

STEP 2 - Run the script (does the rest)
---------------------------------------
1. Connect your tablet with USB debugging on.
2. Right-click DO-IT-ALL.ps1 -> Run with PowerShell
   (Or open PowerShell and run: & "C:\Users\jrrou\tablet-gsi\DO-IT-ALL.ps1")

3. The script will:
   - Extract the GSI image
   - Reboot the tablet to bootloader
   - Flash LineageOS 18.1 + GApps
   - Wipe data and reboot

4. Complete initial setup on the tablet (Wi-Fi, Google account).

STEP 3 - Apply certification + performance (optional)
------------------------------------------------------
After setup, run: APPLY-TWEAKS-AFTER-SETUP.ps1
(With tablet connected.) It will push Tricky Store + Play Integrity Fix
and set animation/PHH tweaks for a smooth experience.

================================================================================

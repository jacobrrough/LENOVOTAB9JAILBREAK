# Lightest GSI with Google Apps (Lenovo Tablet)

You want the **lightest possible GSI** with **Google apps working well** (Play Store, certification, etc.). Best option: **LineageOS 18.1 with GApps** (Android 11). Smaller image, less RAM/CPU use than 21/22.

---

## Recommended: LineageOS 18.1 + GApps (ARM64 A/B)

- **Android 11** – lighter than 14/15.
- **One image** – GApps included, no separate flash.
- **~600 MB compressed** – much smaller than LineageOS 21 Light (~1.3 GB).
- Works with your existing **Magisk + Tricky Store + Play Integrity Fix** setup (reinstall modules after flashing).

---

## Step 1: Download LineageOS 18.1 with GApps

**Browse and pick the ARM64 A/B + GApps file:**

**LineageOS 18.1 (AndyYan):**  
https://sourceforge.net/projects/andyyan-gsi/files/lineage-18.x/

Look for one of these (names may vary slightly by date):

| File pattern | Description |
|--------------|-------------|
| **lineage-18.1-*-arm64_bgN.img.xz** | With GApps, no built-in root (use with Magisk) |
| **lineage-18.1-*-arm64_bgS.img.xz** | With GApps, with PHH Superuser (you can still use Magisk) |

- **bg** = A/B partition + GApps.  
- **N** = no superuser, **S** = with superuser.  
- Pick **arm64_bgN** if you only want Magisk.

**Direct link (check that the file still exists):**  
https://sourceforge.net/projects/andyyan-gsi/files/lineage-18.x/lineage-18.1-20240121-UNOFFICIAL-arm64_bgN.img.xz/download  

If that exact name is gone, use the lineage-18.x folder and choose the newest **arm64_bgN** or **arm64_bgS** `.img.xz`.

1. Download the `.img.xz` to `C:\Users\jrrou\tablet-gsi\`.
2. **Extract** with 7-Zip or WinRAR (right‑click → Extract). You get a `.img` file.
3. Rename the `.img` to **system.img**.

---

## Step 2: Flash (same as before)

Tablet connected, USB debugging on. In a terminal (in the folder with `system.img` and `vbmeta.img`):

```bat
adb reboot bootloader
```

When the tablet is in fastboot:

```bat
fastboot flash system_a system.img
fastboot flash vbmeta vbmeta.img
fastboot flash vbmeta_a vbmeta.img
fastboot flash vbmeta_b vbmeta.img
fastboot -w
fastboot reboot
```

(If your device only has `vbmeta` and no `vbmeta_a`/`vbmeta_b`, use only `fastboot flash vbmeta vbmeta.img`.)

First boot can take 2–5 minutes.

---

## Step 3: After first boot

- Finish setup (Wi‑Fi, Google account).
- **Magisk** is still in boot/init_boot – open Magisk and confirm.
- **Reinstall modules:** Tricky Store, then Play Integrity Fix (from the ZIPs in Download). Reboot.
- Re-apply any **performance tweaks** (animation scale, PHH options) if you like.

---

## If LineageOS 18.1 isn’t available or doesn’t boot

**Fallback: LineageOS 21 Light with GApps** (still lighter than full LineageOS, but heavier than 18.1):

- https://sourceforge.net/projects/andyyan-gsi/files/lineage-21-light/lineage-21.0-20241124-UNOFFICIAL-gsi_arm64_gN-signed.img.gz/download  
- Extract the `.img.gz` → get `.img` → rename to `system.img` and flash the same way.

---

## Summary

| GSI | Android | Size (approx) | GApps |
|-----|---------|----------------|-------|
| **LineageOS 18.1 (bgN/bgS)** | 11 | ~600 MB | ✅ Built-in |
| LineageOS 21 Light (gN) | 14 | ~1.3 GB | ✅ Built-in |

For the **lightest GSI with Google apps working well**, use **LineageOS 18.1 with GApps** (arm64_bgN or arm64_bgS) from the lineage-18.x folder on SourceForge.

# Reduce Lag on LineageOS GSI Tablet

Quick tweaks that usually help. Do the GSI-specific one first if you have it, then the rest.

---

## 1. GSI-specific (if you have "PHH Treble Settings")

Many LineageOS GSIs (TrebleDroid/PHH-based) include **PHH Treble Settings**.

1. Open **Settings** on the tablet.
2. Search for **"PHH"** or scroll to **PHH Treble Settings**.
3. Open **Misc features** (or **Features**).
4. In the **Display** section, enable:
   - **Mediatek GED KPI support**
   - **Disable SF GL backpressure**
5. **Reboot.**

This often reduces UI lag and can help battery a bit. If you don’t see "PHH Treble Settings", skip to section 2.

---

## 2. Developer options – animations and background

1. **Settings → About tablet** → tap **Build number** 7 times (if not already a developer).
2. Go back → **System → Developer options**.
3. Scroll to **Drawing** and set:
   - **Window animation scale** → **0.5x** or **Animation off**
   - **Transition animation scale** → **0.5x** or **Animation off**
   - **Animator duration scale** → **0.5x** or **Animation off**
4. Scroll to **Apps** and set:
   - **Background process limit** → **At most 2 processes** or **At most 3 processes**
5. Optional: **Suspend execution for cached apps** → **On** (can free RAM).

No reboot needed; effect is immediate.

---

## 3. Free up RAM and storage

- **Settings → Storage** → clear caches (e.g. **Free up space** or **Cached data**).
- Uninstall or disable apps you don’t use.
- Keep at least a few GB free; low storage can cause lag.

---

## 4. Keep the system light

- Prefer a **static wallpaper** instead of live/animated.
- Remove heavy widgets or reduce them.
- In **Settings → Apps**, check for apps using a lot of battery/background and restrict background use if you don’t need them running all the time.

---

## 5. Optional: force higher refresh rate (if your tablet supports it)

- **Settings → Display** (or **Developer options**).
- Look for **Refresh rate** and set it to the **highest** (e.g. 90 Hz or 120 Hz).
- Or in **Developer options**, enable **Force peak refresh rate** (smoother but more battery use).

---

## Summary

| What | Where |
|------|--------|
| Mediatek GED KPI + Disable SF GL backpressure | Settings → PHH Treble Settings → Misc features → Display |
| Faster animations | Developer options → Window/Transition/Animator scale → 0.5x or off |
| Fewer background apps | Developer options → Background process limit → 2 or 3 |
| Free space | Settings → Storage → clear cache / remove unused apps |

If it’s still laggy after this, the GSI or Android version may be heavy for your chipset; trying a lighter GSI (e.g. LineageOS 19.1/20 or “Light” build) can help on older or low-RAM tablets.

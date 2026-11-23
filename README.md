# LineageOS 24 for Xiaomi Redmi Note 13 4G NFC (sapphiren)

> ⚠️ **UNOFFICIAL and UNTESTED build. Use at your own risk.**

An unofficial, community-style LineageOS 24 build for the **Xiaomi Redmi Note 13 4G NFC** (codename: `sapphiren`).

This is **not** an official LineageOS release and is not affiliated with, endorsed by, or supported by the LineageOS project or Xiaomi.

---

## ⛔ Disclaimer

**Please read this before you do anything.**

- This build is **untested**. It may not boot, and any feature may be broken.
- This build is **unofficial**. It has no official support and no guarantees.
- Flashing a custom ROM can **brick your phone**, cause **data loss**, void your **warranty**, and break things like banking apps, NFC payments, DRM content and OTA updates.
- **I am not responsible for any damage** to your device or anyone else's. That includes bricked phones, bootloops, lost data, dead SIM cards, hardware failures and anything else that happens after you use this.
- **You choose to flash this. You are responsible for the result.**

If you don't accept that, **don't flash this build.**

---

## 📱 Device

| | |
|---|---|
| Device | Xiaomi Redmi Note 13 4G NFC |
| Codename | `sapphiren` |
| ROM | LineageOS 24 (unofficial) |
| Status | **Untested** |
| Maintainer | *your name here* |

> ⚠️ Only the **NFC** model (`sapphiren`) is targeted. Do **not** flash this on other variants (e.g. the non-NFC `sapphire`), or on other Redmi Note 13 models, unless you know exactly what you are doing.

---

## ✅ / ❌ What works

**Unknown. Nothing has been tested yet.**

| Feature | Status |
|---|---|
| Boot | ❓ Untested |
| Display / touch | ❓ Untested |
| Wi-Fi | ❓ Untested |
| Bluetooth | ❓ Untested |
| Mobile data / calls / SMS | ❓ Untested |
| NFC | ❓ Untested |
| Camera | ❓ Untested |
| Audio | ❓ Untested |
| Fingerprint | ❓ Untested |
| GPS | ❓ Untested |
| Sensors | ❓ Untested |
| Charging | ❓ Untested |

If you test it, please report your results (see [Reporting issues](#-reporting-issues)).

---

## 🧰 Before you start

- Back up **all** your data. Flashing will erase your phone.
- Make sure the battery is charged to at least **50%**.
- Have a **bootloader-unlocked** device (Xiaomi requires an unlock request and a waiting period).
- Install the Android platform-tools (`adb` and `fastboot`) on your PC.
- Make sure your device is exactly **Redmi Note 13 4G NFC (`sapphiren`)**. Check this before you flash.
- Know how to get back to stock (keep the official Xiaomi fastboot ROM for your model).

---

## 🔧 Installation (general outline)

> The exact steps depend on the files in the release. Follow the official LineageOS install guides for similar devices if something is unclear. These steps are a **general outline, not a tested guide.**

1. Unlock the bootloader and enable USB debugging.
2. Download the build files from the release page:
   - the LineageOS 24 ROM `.zip`
   - the recovery image
3. Reboot to fastboot and flash the recovery:
   ```bash
   adb reboot bootloader
   fastboot flash <partition> <recovery.img>
   ```
   *(the correct partition depends on the release)*
4. Boot into recovery.
5. Do a **factory reset / format data**.
6. Choose **Apply update → Apply from ADB** and sideload the ROM:
   ```bash
   adb sideload lineage-24.0-*-sapphiren.zip
   ```
7. Reboot to system.
8. *(Optional)* Flash GApps in the same way **before** the first boot, if you want them.

---

## 🛠️ Building from source

Build environment used: Windows 11 Pro with Linux (WSL), and the usual LineageOS build requirements.

```bash
# 1. Prepare the source tree
mkdir -p ~/android/lineage && cd ~/android/lineage
repo init -u https://github.com/LineageOS/android.git -b lineage-24.0 --git-lfs
repo sync

# 2. Add the device, vendor and kernel trees for sapphiren
#    (see local_manifests / the device tree links for this project)

# 3. Build
source build/envsetup.sh
breakfast sapphiren
brunch sapphiren
```

Notes:

- The branch name (`lineage-24.0`) may differ. Check the LineageOS repositories.
- You need roughly 300 GB of free disk space and 16 GB or more of RAM (a swap file helps).
- No official device tree exists for this phone, so the trees used here are unofficial and may be incomplete.

---

## 🐞 Reporting issues

Since this build is untested, bug reports and test results are welcome. Please include:

- Your exact model and codename
- The build date / version
- What you did and what happened
- A logcat (`adb logcat`) or a `last_kmsg` / `pstore` log if the phone doesn't boot

Please don't ask the official LineageOS team or Xiaomi for support with this build.

---

## 📜 License

LineageOS and the Android Open Source Project are licensed under the Apache License 2.0, and the Linux kernel under GPLv2. Other components keep their own licenses.

This README is provided as-is, with **no warranty of any kind**.

---

## 🙏 Credits

- The [LineageOS](https://lineageos.org) team and contributors
- The Android Open Source Project
- Xiaomi (kernel sources and device resources)
- Everyone who works on device trees and testing for this phone

---

**Reminder: unofficial, untested, flash at your own risk. I'm not responsible for damage to your phone or anyone else's.**


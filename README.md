<img src="logo.svg" alt="Full Krescent logo" width="120">

# Full Krescent

Control lights, motors, pumps and sensors on ESP32 boards from your Android
phone, over Wi-Fi or Bluetooth. Each board belongs to the person who sets it
up: it only obeys their profile and the people they share it with, and every
command is encrypted.

This page holds the downloads. The source code is kept in a separate
repository.

## Download

**[Download the app: full-krescent.apk](https://github.com/Hermes-Bug/full-krescent/releases/latest/download/full-krescent.apk)**
(Android 7 or newer)

Board firmware: pick your chip. Its name is printed on the metal cover of the
board's module.

| Chip | Examples | File |
|---|---|---|
| ESP32 | ESP32-WROOM-32, ESP32-DevKitC | [full-krescent-esp32.bin](https://github.com/Hermes-Bug/full-krescent/releases/latest/download/full-krescent-esp32.bin) |
| ESP32-S3 | ESP32-S3-WROOM-1, ESP32-S3-DevKitC | [full-krescent-esp32s3.bin](https://github.com/Hermes-Bug/full-krescent/releases/latest/download/full-krescent-esp32s3.bin) |
| ESP32-C3 | ESP32-C3-DevKitM, ESP32-C3 SuperMini | [full-krescent-esp32c3.bin](https://github.com/Hermes-Bug/full-krescent/releases/latest/download/full-krescent-esp32c3.bin) |
| ESP32-C6 | ESP32-C6-DevKitC | [full-krescent-esp32c6.bin](https://github.com/Hermes-Bug/full-krescent/releases/latest/download/full-krescent-esp32c6.bin) |

Every version, with what changed: [Releases](https://github.com/Hermes-Bug/full-krescent/releases).

## Install the app

1. On your phone, tap the app download link above.
2. Open the downloaded file. Android asks to allow installs from your browser
   (or Files app): allow it for that app only.
3. If Play Protect warns about an unknown developer, tap **More details →
   Install anyway**. It says this because the app is not from the Play Store.

There are no automatic updates, so come back here now and then. A newer
version installs over the old one and keeps your profiles and boards.

## Put the firmware on a board

You need the board's USB cable and a computer with Chrome or Edge.

1. Download the file for your chip from the table above.
2. Plug the board in and open Espressif's web flasher:
   <https://espressif.github.io/esptool-js/>
3. Click **Connect** and pick the board's port. If none shows up, hold the
   board's **BOOT** button, tap **RESET** (or **EN**), let go of BOOT, and try
   again.
4. Set **Flash Address** to `0x0`, choose the file, and click **Program**. It
   takes about a minute.
5. Click **Disconnect**, open the **Console** on the same page (115200 baud)
   and press RESET. The board prints its **setup code** (16 characters, like
   `7K2M-9QXA-4BTR-1HZP`) and a QR code. Write the code down or put it on a
   sticker on the board: you need it to set the board up.

## Set up

1. Open the app and create a profile: a username and a password. Keep the
   **recovery code** it shows somewhere safe.
2. On **Boards**, tap **+**. A new board accepts an owner for 2 minutes after
   it powers on; press its BOOT button once for 2 more minutes.
3. Scan or type the setup code. The board is now yours. Share it with others
   from the board's page.

**New phone?** On the old phone, go to Settings → your profile → **Move to a
new phone**. On the new phone, tap **Move from another phone**. To be ready
for a lost phone, save a **backup file** from the same place and keep it
somewhere private, such as your Google Drive.

## Is my download genuine?

Each release has a `SHA256SUMS.txt` file with the checksum of every download.
The app is signed with Full Krescent's own key. Its certificate's SHA-256
fingerprint is:

```
32:BB:00:9B:40:06:C0:49:DB:DF:21:E4:04:B1:46:AE:09:7D:97:DA:40:F7:F8:A7:CC:A3:D1:5A:D8:E0:0B:4F
```

On a computer with the Android SDK, `apksigner verify --print-certs
full-krescent.apk` shows it.

## Privacy

Full Krescent has no account, no ads and no analytics, and it sends nothing
to any server. It talks only to your own boards, over your Wi-Fi or
Bluetooth. Your profiles stay on your phone, encrypted with your password.
Backup files go only where you choose to save them.

What the app asks for, and why:

| Permission | Why |
|---|---|
| Bluetooth | To find your boards and talk to them |
| Location | Android requires it to scan for Bluetooth devices on Android 11 and older |
| Camera | To scan QR codes (a board's setup code, an invite, moving to a new phone) |
| Fingerprint or face | Optional, to unlock your profile without typing the password |

## Problems or questions

Open an issue: [Issues](https://github.com/Hermes-Bug/full-krescent/issues).

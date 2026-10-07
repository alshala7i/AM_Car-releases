# AM_Car — release channel

Public distribution and update channel for **AM_Car**, the in-car control suite.
Published by **@AM_CarApp** (TikTok · Instagram). © 2026 AM_Car — All rights reserved.

## Install

```bash
adb install -r AM_Car-1.9.5.apk
```

Only the newest build is kept here — publishing a release replaces the previous one, so the
repository always holds exactly one APK plus `latest.json`.

Then open AM_Car, copy the **vehicle device code** from the activation screen and send it to
`@AM_CarApp`. The licence file you receive goes to:

```bash
adb push amcar.lic /sdcard/Android/data/com.amcar.app/files/amcar.lic
```

## Why the APK is public and still useless without a licence

AM_Car's own interface ships **encrypted** inside the APK (AES-256-GCM). The key that decrypts it
exists only inside a signed licence file, and licences are signed with a key that only AM_Car
holds. An unlicensed copy installs, shows the activation screen and can render nothing else.

## `latest.json`

The update manifest the installed app polls (`versionCode`, `versionName`, `apk`, `sha256`).
Never edit it by hand — `tools/make_release.py` in the source repository writes it.

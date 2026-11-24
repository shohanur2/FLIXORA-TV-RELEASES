# FLIXORA TV Releases

This repository is the **only update source for FLIXORA Android TV / Google TV**.

- Mobile FLIXORA updates must never be published here.
- TV releases use tags in the format `tv-vMAJOR.MINOR.PATCH` (example: `tv-v1.0.16`).
- Every release must include one universal TV APK named `FLIXORA-TV-<version>.apk`.
- The TV app checks only the latest release in this repository and accepts only APK assets whose filename starts with `FLIXORA-TV-`.
- The app verifies the APK package name, version name and a strictly higher version code before opening Android's installer.

## Publishing

1. In the `shohanur2/FLIXORA-TV` repository, run **Build FLIXORA TV APK** manually.
2. Set `publish_release` to **true** only when the build is intended for visitors.
3. The workflow builds and tests the TV app, uploads the normal 14-day Actions artifact, then publishes the APK here.
4. The workflow requires the `FLIXORA_TV_RELEASE_TOKEN` Actions secret in `FLIXORA-TV`. It must be a fine-grained GitHub token with **Contents: Read and write** access to this repository.
5. The TV APK must be signed with the same persistent signing key as the installed TV app. Never publish a debug-signed APK as an update.

## Safety

Do not upload mobile APKs, test APKs, or artifacts from `FLIXORA-BOX` here. Do not change the TV package ID or signing key for an in-place update.

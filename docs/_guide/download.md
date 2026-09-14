---
title: Download
description: Get ZapFast for Linux, macOS, or Windows, with install instructions for each.
nav_order: 1
---

{% assign v = site.zapfast_version %}
{% assign name = site.release_asset_prefix %}
{% assign app = site.release_app_name %}
{% assign base = "https://github.com/crmne/zapfast/releases/download/v" | append: v %}

ZapFast was previously called FastsApp. The current published release still
uses that name; builds from source use ZapFast.

The current version is **v{{ v }}**. SHA-256 checksums are in
[checksums.txt]({{ base }}/checksums.txt). Older versions are on the
[releases page](https://github.com/crmne/zapfast/releases).

## Linux

On Arch Linux and derivatives, install from the
[AUR](https://aur.archlinux.org/packages/{{ name }}-bin):

```sh
paru -S {{ name }}-bin   # prebuilt
paru -S {{ name }}       # builds from the release source
paru -S {{ name }}-git   # builds from the latest commit
```

For other distributions, download a tarball with the binary, desktop file,
and icon:

- [{{ name }}-v{{ v }}-x86_64-unknown-linux-gnu.tar.gz]({{ base }}/{{ name }}-v{{ v }}-x86_64-unknown-linux-gnu.tar.gz)
- [{{ name }}-v{{ v }}-aarch64-unknown-linux-gnu.tar.gz]({{ base }}/{{ name }}-v{{ v }}-aarch64-unknown-linux-gnu.tar.gz)

{{ app }} needs the standard egui libraries and ALSA:
`libglvnd`, `libxkbcommon`, `wayland`, `libx11`, and `alsa-lib` (on
Debian or Ubuntu: `libasound2`, `libgl1`, `libxkbcommon0`, `libwayland-client0`).
For color emoji, install `noto-fonts-emoji` (`fonts-noto-color-emoji` on
Debian). The file picker uses `xdg-desktop-portal`.

## macOS

One download for both Apple Silicon and Intel:

- [{{ name }}-v{{ v }}-macos-universal.dmg]({{ base }}/{{ name }}-v{{ v }}-macos-universal.dmg)

Open it and drag **{{ app }}** to Applications.

### First open on macOS

This build is not notarized, so macOS blocks it the first time. Allow it in
Privacy & Security:

1. Double-click **{{ app }}** in Applications. macOS says it cannot be
   opened because Apple cannot check it for malicious software. Click
   **Done**, not **Move to Trash**.
2. Open **System Settings**, then **Privacy & Security**.
3. Scroll down to the **Security** section, find *"{{ app }} was blocked to
   protect your Mac"*, and click **Open Anyway**.
4. Authenticate, then click **Open Anyway** once more.

You can also clear the quarantine flag:

```sh
xattr -dr com.apple.quarantine /Applications/{{ app }}.app
```

The `-r` also clears the flag from files inside the app bundle.

## Windows

The installer adds {{ app }} to the Start menu and needs no administrator
rights. Choose x86_64 for most PCs or aarch64 for Windows on ARM:

- [{{ name }}-v{{ v }}-x86_64-pc-windows-msvc-setup.exe]({{ base }}/{{ name }}-v{{ v }}-x86_64-pc-windows-msvc-setup.exe)
- [{{ name }}-v{{ v }}-aarch64-pc-windows-msvc-setup.exe]({{ base }}/{{ name }}-v{{ v }}-aarch64-pc-windows-msvc-setup.exe)

To run {{ app }} without installing it, download a zip, extract it, and run
`{{ name }}.exe`.

- [{{ name }}-v{{ v }}-x86_64-pc-windows-msvc.zip]({{ base }}/{{ name }}-v{{ v }}-x86_64-pc-windows-msvc.zip)
- [{{ name }}-v{{ v }}-aarch64-pc-windows-msvc.zip]({{ base }}/{{ name }}-v{{ v }}-aarch64-pc-windows-msvc.zip)

SmartScreen may warn about an unknown publisher on first run. Choose **More
info**, then **Run anyway**.

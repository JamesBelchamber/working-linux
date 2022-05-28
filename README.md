# Working Linux

Working Linux is a light-touch rebuild of [Fedora Silverblue](https://silverblue.fedoraproject.org/) with the following goals:

- Building a Workstation image that closely tracks Fedora Workstation (for new users 😁)
- Building a Minimal image containing only essential applications (for power users 😎)

New users will see the real power of Silverblue's unique combination of flatpaks and rpm-ostree in delivering a capable replacement for Fedora Workstation, leveraging modern Flatpaks alongside mature RPMs. Power users can pick and choose what to layer on their own, without having unwanted applications in their base image.

## Installation

Working Linux is an alternative image for Fedora Silverblue, so be sure to [install Silverblue](https://silverblue.fedoraproject.org/download) first. Once done, open up a Terminal and run the following commands:

```bash
sudo ostree remote add --no-gpg-verify working-linux https://jamesbelchamber.github.io/working-linux

rpm-ostree rebase working-linux:working-linux/36/x86_64/workstation
```

To install the minimal image just change `workstation` to `minimal` in the rebase.

## Differences vs Fedora Silverblue

### Summary

| Application                | Minimal | Silverblue | Workstation |
|----------------------------|---------|------------|-------------|
| Firefox                    | ❌       | ✅          | ✅           |
| Fedora Desktop Backgrounds | ❌       | ✅          | ✅           |
| GNOME Disks                | ❌       | ✅          | ✅           |
| GNOME Tour*                | ✅       | ✅          | ✅           |
| GNOME Help                 | ❌       | ✅          | ✅           |
| GNOME Shell Extensions**   | ❌       | ✅          | ✅           |
| GNOME Photos               | ❌       | ❌          | ✅           |
| Gnome Videos               | ❌       | ❌          | ✅           |
| Document Scanner           | ❌       | ❌          | ✅           |
| Rhythmbox                  | ❌       | ❌          | ✅           |
| Cheese                     | ❌       | ❌          | ✅           |
| Problem Reporting          | ❌       | ❌          | ✅           |
| GNOME Boxes***              | ❌       | ❌          | ❌           |

\* This is a weak dependency for GNOME Shell, which rpm-ostree cannot currently disable (tracked in [this issue](https://github.com/coreos/rpm-ostree/issues/718))
\** Classic Session, Applications Menu, Background Logo, Launch new instance, Places Status Indicator, Window List and Common.
\*** This brings in 197 packages (!) and is available as a Flatpak on Flathub.

### Detailed

<details>
<summary>Full list of packages added by Workstation vs Silverblue</summary>

```
  LibRaw-0.20.2-5.fc36.x86_64
  SDL2-2.0.22-2.fc36.x86_64
  abrt-libs-2.15.1-1.fc36.x86_64
  augeas-libs-1.13.0-2.fc36.x86_64
  babl-0.1.92-1.fc36.x86_64
  baobab-42.0-1.fc36.x86_64
  brasero-libs-3.12.3-1.fc36.x86_64
  cheese-2:41.1-2.fc36.x86_64
  deltarpm-3.6.2-11.fc36.x86_64
  dleyna-connector-dbus-0.3.0-12.fc36.x86_64
  dleyna-core-0.6.0-13.fc36.x86_64
  dleyna-renderer-0.6.0-14.fc36.x86_64
  dleyna-server-0.6.0-13.fc36.x86_64
  dnf-data-4.12.0-1.fc36.noarch
  flexiblas-3.2.0-2.fc36.x86_64
  flexiblas-netlib-3.2.0-2.fc36.x86_64
  flexiblas-openblas-openmp-3.2.0-2.fc36.x86_64
  frei0r-plugins-1.7.0-14.fc36.x86_64
  gavl-1.4.0-20.fc36.x86_64
  gegl04-0.4.36-1.fc36.x86_64
  gfbgraph-0.2.4-2.fc36.x86_64
  gnome-abrt-1.4.1-3.fc36.x86_64
  gnome-online-miners-3.34.0-10.fc36.x86_64
  gnome-photos-42.0-2.fc36.x86_64
  gnome-video-effects-0.5.0-7.fc36.noarch
  gom-0.4-7.fc36.x86_64
  grilo-0.3.14-2.fc36.x86_64
  grilo-plugins-0.3.14-3.fc36.x86_64
  gstreamer1-plugins-good-gtk-1.20.0-1.fc36.x86_64
  imath-3.1.5-1.fc36.x86_64
  jasper-libs-2.0.33-2.fc36.x86_64
  libcomps-0.1.18-2.fc36.x86_64
  libdazzle-3.44.0-1.fc36.x86_64
  libdecor-0.1.0-2.fc36.x86_64
  libdmapsharing-2.9.41-6.fc36.x86_64
  libgdither-0.6-26.fc36.x86_64
  libgfortran-12.1.1-1.fc36.x86_64
  libgpod-0.8.3-41.fc36.x86_64
  liboauth-1.0.3-18.fc36.x86_64
  libpeas-1.32.0-1.fc36.x86_64
  libpeas-gtk-1.32.0-1.fc36.x86_64
  libpeas-loader-python3-1.32.0-1.fc36.x86_64
  libquadmath-12.1.1-1.fc36.x86_64
  libreport-2.17.1-1.fc36.x86_64
  libreport-gtk-2.17.1-1.fc36.x86_64
  libreport-plugin-reportuploader-2.17.1-1.fc36.x86_64
  libreport-web-2.17.1-1.fc36.x86_64
  libtomcrypt-1.18.2-14.fc36.x86_64
  libtommath-1.2.0-7.fc36.x86_64
  media-player-info-23-10.fc36.noarch
  openblas-0.3.19-3.fc36.x86_64
  openblas-openmp-0.3.19-3.fc36.x86_64
  openexr-libs-3.1.5-1.fc36.x86_64
  python3-beaker-1.10.0-13.fc36.noarch
  python3-beautifulsoup4-4.11.0-1.fc36.noarch
  python3-cffi-1.15.0-5.fc36.x86_64
  python3-crypto-2.6.1-39.fc36.x86_64
  python3-cryptography-36.0.0-3.fc36.x86_64
  python3-dnf-4.12.0-1.fc36.noarch
  python3-gpg-1.15.1-6.fc36.x86_64
  python3-hawkey-0.67.0-2.fc36.x86_64
  python3-humanize-3.13.1-3.fc36.noarch
  python3-libcomps-0.1.18-2.fc36.x86_64
  python3-libdnf-0.67.0-2.fc36.x86_64
  python3-libreport-2.17.1-1.fc36.x86_64
  python3-lxml-4.7.1-2.fc36.x86_64
  python3-mako-1.1.4-7.fc36.noarch
  python3-markupsafe-2.0.0-3.fc36.x86_64
  python3-paste-3.5.0-6.fc36.noarch
  python3-ply-3.11-15.fc36.noarch
  python3-pyOpenSSL-21.0.0-2.fc36.noarch
  python3-pycparser-2.20-6.fc36.noarch
  python3-soupsieve-2.3.1-3.fc36.noarch
  python3-tempita-0.5.2-2.fc35.noarch
  python3-unbound-1.15.0-1.fc36.x86_64
  rhythmbox-3.4.4-12.fc36.x86_64
  rpm-plugin-systemd-inhibit-4.17.0-10.fc36.x86_64
  satyr-0.39-4.fc36.x86_64
  sg3_utils-libs-1.46-3.fc36.x86_64
  simple-scan-42.1-1.fc36.x86_64
  suitesparse-5.10.1-2.fc36.x86_64
  tbb-2020.3-9.fc35.x86_64
  totem-1:42.0-1.fc36.x86_64
  unbound-libs-1.15.0-1.fc36.x86_64
  xmlrpc-c-1.51.0-14.fc36.x86_64
  xmlrpc-c-client-1.51.0-14.fc36.x86_64
```
</details>

<details>
<summary>Full list of packages removed by Minimal vs Silverblue (XXMB)</summary>

```
TODO
```
</details>

## Documentation and Help

- For documentation, please refer to the official docs:
  - [Fedora Silverblue](https://docs.fedoraproject.org/en-US/fedora-silverblue/)
  - [Fedora Workstation](https://docs.fedoraproject.org/en-US/fedora/latest/)
- For help, use the official channels:
  - Fedora Discussion ([#silverblue](https://discussion.fedoraproject.org/tag/silverblue))
  - Libera Chat ([#silverblue](https://web.libera.chat/#silverblue))
  - Matrix ([#silverblue:fedoraproject.org](https://matrix.to/#/#silverblue:fedoraproject.org))
- If you think there's an issue specific to Working Linux, reach out to me on Matrix ([@jamesbelchamber:matrix.org](https://matrix.to/#/@jamesbelchamber:matrix.org))

## Contributing
Pull requests are welcome, but only in pursuit of the project goals:

- ✅ A change to the Workstation image to better align with Fedora Workstation
- ✅ A change to the Minimal image to remove unnecessary packages
- ❌ A change to the Workstation image that deviates from Fedora Workstation
  - Raise the issue with the [Fedora Workstation Working Group](https://docs.fedoraproject.org/en-US/workstation-working-group/)
- ❌ A change to the unique Silverblue components (e.g. `rpm-ostree`)
  - Raise the issue with [Team Silverblue](https://github.com/fedora-silverblue/issue-tracker/issues)

## License
[MIT](https://choosealicense.com/licenses/mit/)
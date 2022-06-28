# Working Linux

Working Linux is a light-touch rebuild of [Fedora Silverblue](https://silverblue.fedoraproject.org/) with the following goals:

- Building a Workstation image that closely tracks Fedora Workstation (for new users 😁)
- Building a Minimal image containing only essential applications (for power users 😎)

New users will see the real power of Silverblue's unique combination of flatpaks and rpm-ostree in delivering a capable replacement for Fedora Workstation, leveraging modern Flatpaks alongside mature RPMs. Power users can pick and choose what to layer on their own, without having unwanted applications in their base image.

## Installation

Download the Workstation ISO from [here](https://jamesbelchamber.github.io/working-linux/iso).

If you have already installed Silverblue you can rebase to Working Linux - just open up a Terminal and run the following commands:

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
<summary>Full list of packages added by Workstation (vs Silverblue)</summary>

```
  LibRaw
  SDL2
  abrt-libs
  augeas-libs
  babl
  baobab
  brasero-libs
  cheese
  deltarpm
  dleyna-connector-dbus
  dleyna-core
  dleyna-renderer
  dleyna-server
  dnf-data
  flexiblas
  flexiblas-netlib
  flexiblas-openblas-openmp
  frei0r-plugins
  gavl
  gegl04
  gfbgraph
  gnome-abrt
  gnome-online-miners
  gnome-photos
  gnome-video-effects
  gom
  grilo
  grilo-plugins
  gstreamer1-plugins-good-gtk
  imath
  jasper-libs
  libcomps
  libdazzle
  libdecor
  libdmapsharing
  libgdither
  libgfortran
  libgpod
  liboauth
  libpeas
  libpeas-gtk
  libpeas-loader-python3
  libquadmath
  libreport
  libreport-gtk
  libreport-plugin-reportuploader
  libreport-web
  libtomcrypt
  libtommath
  media-player-info
  openblas
  openblas-openmp
  openexr-libs
  python3-beaker
  python3-beautifulsoup4
  python3-cffi
  python3-crypto
  python3-cryptography
  python3-dnf
  python3-gpg
  python3-hawkey
  python3-humanize
  python3-libcomps
  python3-libdnf
  python3-libreport
  python3-lxml
  python3-mako
  python3-markupsafe
  python3-paste
  python3-ply
  python3-pyOpenSSL
  python3-pycparser
  python3-soupsieve
  python3-tempita
  python3-unbound
  rhythmbox
  rpm-plugin-systemd-inhibit
  satyr
  sg3_utils-libs
  simple-scan
  suitesparse
  tbb
  totem
  unbound-libs
  xmlrpc-c
  xmlrpc-c-client
```
</details>

<details>
<summary>Full list of packages removed by Minimal (vs Silverblue)</summary>

```
  desktop-backgrounds-gnome
  f36-backgrounds-base
  f36-backgrounds-gnome
  fedora-bookmarks
  firefox
  gnome-classic-session
  gnome-disk-utility
  gnome-shell-extension-apps-menu
  gnome-shell-extension-background-logo
  gnome-shell-extension-common
  gnome-shell-extension-launch-new-instance
  gnome-shell-extension-places-menu
  gnome-shell-extension-window-list
  yelp
  yelp-libs
  yelp-xsl
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
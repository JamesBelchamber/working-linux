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

| Application      | Minimal | Silverblue | Workstation |
|------------------|---------|------------|-------------|
| Firefox          | ❌       | ✅          | ✅           |
| GNOME Disks      | ❌       | ✅          | ✅           |
| GNOME Tour       | ❌       | ✅          | ✅           |
| GNOME Help       | ❌       | ✅          | ✅           |
| GNOME Photos     | ❌       | ❌          | ✅           |
| Gnome Videos     | ❌       | ❌          | ✅           |
| Document Scanner | ❌       | ❌          | ✅           |
| Rhythmbox        | ❌       | ❌          | ✅           |
| Cheese           | ❌       | ❌          | ✅           |

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
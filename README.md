cyberlinux-profiles
[![build-badge](https://travis-ci.com/phR0ze/cyberlinux-profiles.svg?branch=master)](https://travis-ci.com/phR0ze/cyberlinux-profiles)
[![license-badge](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
====================================================================================================

<img align="left" width="48" height="48" src="https://raw.githubusercontent.com/phR0ze/cyberlinux/master/art/logo_256x256.png">
<b>cyberlinux-profiles</b> provides the Arch Linux packaging of configuration for the different
pre-baked deployment flavors being maintained for the <b>cyberlinux project</b>.

### Disclaimer
***cyberlinux-config*** comes with absolutely no guarantees or support of any kind. It is to be used at
your own risk.  Any damages, issues, losses or problems caused by the use of ***cyberlinux-config*** are
strictly the responsiblity of the user and not the developer/creator of ***cyberlinux-config***.

**Licensing/copyright use restrictions depend on the packages included in the profile**.  Profiles that
are restricted in their use to ***personal use only*** have the keyword ***personal*** in the naming
of that profile. Additionally profiles aimed at specific hardware have been named with a trailing
**arch** called out.

### Table of Contents
* [Usage](#usage)
  * [Install dependencies](#install-dependencies)
  * [Build packages](#build-packages)
* [Contributions](#contributions)
  * [Git-Hook Version Increment](#git-hook-version-increment)
* [Licenses](#licenses)
  * [Contribution](#contribution)
* [Backlog](#backlog)
* [Changelog](#changelog)

---

# Usage <a name="usage"/></a>

## Install dependencies <a name="install-dependencies"/></a>
1. Install dependency packages for building
   ```bash
   $ sudo pacman -S arch-install-scripts pacman-contrib pacman
   ```

## Build packages <a name="build-packages"/></a>
```bash
$ makepkg -s
```

## Contribute <a name="Contribute"/></a>
Pull requests are always welcome.  However understand that they will be evaluated purely on whether
or not the change fits with my goals/ideals for the project.

### Git-Hook Version Increment <a name="git-hook-version-increment"/></a>
Enable the githooks to have automatic version increments

```bash
cd ~/Projects/cyberlinux-profiles
git config core.hooksPath .githooks
```

## License <a name="license"/></a>
Licensed under either of:
 * MIT license [LICENSE-MIT](LICENSE-MIT) or http://opensource.org/licenses/MIT
 * Apache License, Version 2.0 [LICENSE-APACHE](LICENSE-APACHE) or http://www.apache.org/licenses/LICENSE-2.0

## Contribution <a name="contribution"/></a>
Unless you explicitly state otherwise, any contribution intentionally submitted for inclusion in
this project by you, as defined in the Apache-2.0 license, shall be dual licensed as above, without
any additional terms or conditions.

---

# Backlog <a name="backlog"/></a>
* Build bootable USB with custom menus

# Changelog <a name="changelog"/></a>

<div align="center">

# asdf-brew-php [![Build](https://github.com/skillshare/asdf-brew-php/actions/workflows/build.yml/badge.svg)](https://github.com/skillshare/asdf-brew-php/actions/workflows/build.yml) [![Lint](https://github.com/skillshare/asdf-brew-php/actions/workflows/lint.yml/badge.svg)](https://github.com/skillshare/asdf-brew-php/actions/workflows/lint.yml)

[brew-php](https://github.com/Skillshare/asdf-brew-php) plugin for the [asdf version manager](https://asdf-vm.com).

</div>

Why this plugin? Compiling PHP is not deterministic on macOS. Relying
on existing [brew](https://brew.sh) bottles is more deterministic.
This plugin trades off compiling an explicit major, minor, and patch
level PHP for whatever precompiled major and minor version is
available in brew.

# Contents

- [Dependencies](#dependencies)
- [Install](#install)
- [Contributing](#contributing)
- [License](#license)
- [FAQ](#faq)

# Dependencies

- `brew`

# Install

Plugin:

```shell
asdf plugin add brew-php
# or
asdf plugin add brew-php https://github.com/Skillshare/asdf-brew-php.git
```

brew-php:

```shell
# Show all installable versions
asdf list-all brew-php

# Install specific version
asdf install brew-php latest

# Install a given minor version
asdf install brew-php 8.4

# Set a version globally (on your ~/.tool-versions file)
asdf global brew-php latest

# Now brew-php commands are available
php --version
```

Check [asdf](https://github.com/asdf-vm/asdf) readme for more instructions on how to
install & manage versions.

# Contributing

Contributions of any kind welcome! See the [contributing guide](contributing.md).

[Thanks goes to these contributors](https://github.com/skillshare/asdf-brew-php/graphs/contributors)!

## How to list versions

```shell
bin/list-all
```

## How to install a version

You can run the plugin scripts independent of `asdf`. `asdf` calls the
script with the expected environment variables. [See the
docs](https://asdf-vm.com/plugins/create.html#bin-install).

```shell
$ env ASDF_INSTALL_TYPE=version ASDF_INSTALL_VERSION=8.4 ASDF_INSTALL_PATH=tmp/8.4 bin/install
$ tmp/8.4/bin/php --version
```

# License

See [LICENSE](LICENSE) © [Skillshare Inc.](https://github.com/Skillshare)

# FAQ

## How does this work?

The plugin relies on versioned formulae (`php@8.3`, `php@8.2` etc) in
brew. The formulas come "bottled", meaning they are precompiled for
specific macOS versions. The pluging installs a brew formula then
links it to asdf install directory.

## What versions are supported?

8.1, 8.2, 8.3, and 8.4 at the time of this writing.

## Why are patch versions not supported?

The plugin relies on Brew formulae. Those are only pinned to minor
versions. So you can only install a minor version. The current formula
determines the patch version.

## What are the trade-offs with this approach?

The obvious trade-off is patch level version management. Relying on
brew also means the patch level may change when running `brew upgrade`
or `brew update`. So for example, say `.tool-versions` contains
`brew-php 8.4`. `asdf install` would install the `php@8.4` formula.
The formula may be set to use `8.4.1`. A future `brew update` could
update `php@8.4` to `8.4.5`. Now that `brew-php 8.4` would use
`8.4.5`.

## Are there other limitations?

- Installing "ref" say a path to a brew formula definition or a gitref
  are not suppored.

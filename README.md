<div align="center">

# asdf-brew-php [![Build](https://github.com/skillshare/asdf-brew-php/actions/workflows/build.yml/badge.svg)](https://github.com/skillshare/asdf-brew-php/actions/workflows/build.yml) [![Lint](https://github.com/skillshare/asdf-brew-php/actions/workflows/lint.yml/badge.svg)](https://github.com/skillshare/asdf-brew-php/actions/workflows/lint.yml)

[brew-php](https://github.com/Skillshare/asdf-brew-php) plugin for the [asdf version manager](https://asdf-vm.com).

</div>

Why this plugin? Compiling PHP is not deterministic on macOS. Relying
on existing [brew][https://brew.sh] bottles is more deterministic.
This plugin trades off compiling an explicit major, minor, and patch
level PHP for whatever precompiled major and minor version is
available in brew.

# Contents

- [Dependencies](#dependencies)
- [Install](#install)
- [Contributing](#contributing)
- [License](#license)

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

# License

See [LICENSE](LICENSE) © [Skillshare Inc.](https://github.com/Skillshare)

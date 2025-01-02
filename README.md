<div align="center">

# asdf-brew-php [![Build](https://github.com/ahawkins/asdf-brew-php/actions/workflows/build.yml/badge.svg)](https://github.com/ahawkins/asdf-brew-php/actions/workflows/build.yml) [![Lint](https://github.com/ahawkins/asdf-brew-php/actions/workflows/lint.yml/badge.svg)](https://github.com/ahawkins/asdf-brew-php/actions/workflows/lint.yml)

[brew-php](https://github.com/Skillshare/asdf-brew-php) plugin for the [asdf version manager](https://asdf-vm.com).

</div>

# Contents

- [Dependencies](#dependencies)
- [Install](#install)
- [Contributing](#contributing)
- [License](#license)

# Dependencies

**TODO: adapt this section**

- `bash`, `curl`, `tar`, and [POSIX utilities](https://pubs.opengroup.org/onlinepubs/9699919799/idx/utilities.html).
- `SOME_ENV_VAR`: set this environment variable in your shell config to load the correct version of tool x.

# Install

Plugin:

```shell
asdf plugin add brew-php
# or
asdf plugin add brew-php https://github.com/ahawkins/asdf-brew-php.git
```

brew-php:

```shell
# Show all installable versions
asdf list-all brew-php

# Install specific version
asdf install brew-php latest

# Set a version globally (on your ~/.tool-versions file)
asdf global brew-php latest

# Now brew-php commands are available
php --version
```

Check [asdf](https://github.com/asdf-vm/asdf) readme for more instructions on how to
install & manage versions.

# Contributing

Contributions of any kind welcome! See the [contributing guide](contributing.md).

[Thanks goes to these contributors](https://github.com/ahawkins/asdf-brew-php/graphs/contributors)!

# License

See [LICENSE](LICENSE) © [Adam Hawkins](https://github.com/ahawkins/)

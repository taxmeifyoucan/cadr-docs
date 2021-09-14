---
description: This page documents how to develop this repository.
---

# Contributing

## Development 

For information how to develop applications that integrate into this repository easily, use time machine and read it in the future.

**If you're not a developer, this page is useless to you.**

### Building

The only officially supported OS for building and running is currently **Debian 10 \(Buster\)**! Contributions to test and fix **running** of this repository on other Debian-based systems welcome!

Only needed for the first time:

```text
git clone https://github.com/Kixunil/cryptoanarchy-deb-repo-builder
cd cryptoanarchy-deb-repo-builder
sudo apt-get install cargo npm ruby-mustache
# Requires the latest debcrafter version
cargo install --git https://github.com/Kixunil/debcrafter
PATH=$PATH:~/.cargo/bin
cargo install cfg_me
make BUILD_DIR=$PWD/build build-dep
```

For all subsequent builds:

```text
make BUILD_DIR=$PWD/build
```

### Packaging new software

Packages in the repository are created using [debcrafter](https://github.com/Kixunil/debcrafter) tool which allows building complex debian packages from _very rich_ specification files. Packaging process is still being developed and not fully documented yet.   
  
**Recommended approach to learn about packaging and creating own package is using** [**cadr-guide**](%20https://github.com/debian-cryptoanarchy/cadr-guide)**.** This interactive tool will guide you through the process and help you create a package for your desired software. 


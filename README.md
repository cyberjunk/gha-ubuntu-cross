# Github Action for Cross-Compile Support on Ubuntu

[![CI](https://github.com/cyberjunk/gha-ubuntu-cross/actions/workflows/main.yml/badge.svg)](https://github.com/cyberjunk/gha-ubuntu-cross/actions/workflows/main.yml)

### Description

* Requires AMD64 Ubuntu 18.04, 20.04 or 22.04
* Adds Ubuntu APT package repository for input parameter `arch`.
* Installs basic dev packages for input parameter `arch`:
  * libstdc++-10-dev-`$arch`-cross (20.04 and 22.04 only)
  * libstdc++6-`$arch`-cross
  * libc6-dev-`$arch`-cross
  * linux-libc-dev-`$arch`-cross

### Input Parameter: arch

Must be one of the valid Ubuntu architectures. Tested with:

* arm64
* armhf
* i386

### Example
 
```bash
  steps:
  
  - name: Install Cross-Compile Support (ARM64)
    uses: cyberjunk/gha-ubuntu-cross@v1
    with:
      arch: arm64
      
  - name: Install libx11-dev for ARM64
    run: sudo apt-get install libx11-dev:arm64
    
```

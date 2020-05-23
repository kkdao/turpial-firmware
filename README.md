<p align="center">
  <a href="https://locha.io/">
  <img height="200px" src="doc/LogotipoTurpial-Color.20-09-19.svg">
  </a>
  <br>
  <a href="https://travis-ci.com/btcven/turpial-firmware">
    <img src="https://travis-ci.com/btcven/turpial-firmware.svg?branch=master" title="Build Status">
  </a>
</p>

<p align="center">
  <a href="https://locha.io/">Project Website</a> |
  <a href="https://btcven.github.io/turpial-firmware/">Code Documentation</a> |
  <a href="https://locha.io/donate">Donate</a> |
  <a href="https://github.com/sponsors/rdymac">Sponsor</a> |
  <a href="https://locha.io/buy">Buy</a>
</p>

<h1 align="center">Turpial Firmware</h1>

Welcome, and thank you for your visit. Here you can
find the main firmware for the Turpial device, compatible with Locha Mesh and be aware
of our development process.

## About Locha Mesh

The Locha Mesh network is a secure radio network for off-grid messaging, Bitcoin and other
cryptocurrencies transactions without access to the Internet. The main objective is a
long range network for everyone and
everywhere. For this reason, we are working not only in a protocol, but also in the
firmware for affordable devices like our **Turpial**.

If you want to learn more about Locha Mesh, feel free to read
[the Locha Mesh main repository](https://github.com/btcven/locha) or take a
look at our website [locha.io](https://www.locha.io).

## Sponsor

If you want to support this project you can make a donation to the Locha Mesh
effort to build private censorship-resistant mesh network devices for Bitcoin and other
cryptocurrencies transactions without Internet.

Here are some places if you want to support us:

- Donate: https://locha.io/donate
- Buy Turpial devices: https://locha.io/buy

## Supported ESP32 boards

Currently we use the [ESP-WROVER-KIT](https://www.espressif.com/en/products/hardware/esp-wrover-kit/overview)
development board to test the code and the radio module, although other ESP32
boards can be used as long as it fits on the flash memory. It should work on
both the WROOM and WROVER chips without changes on the code.

The board connects over UART to the
[SimpleLink CC1312R](https://www.ti.com/product/CC1312R) radio module, the
pinout is yet to be decided in the final complete board design. See the
[radio-firmware](https://github.com/btcven/radio-firmware) repository for more
information on the radio module we use.

## Table of Contents

[Turpial Firmware](#turpial-firmware)

[About Locha Mesh](#about-locha-mesh)

[Sponsor](#sponsor)

[Supported ESP32 boards](#supported-esp32-boards)

* [Getting Started](#getting-started)
   - [Development Workflow.](#development-workflow)
   - [Installing ESP-IDF.](#installing-esp-idf)
   - [Compiling.](#compiling)
   - [Flashing the Firmware](#flashing-the-firmware)
   - [Running Tests](#running-tests)
   - [Compiling Documentation.](#compiling-documentation)

[License](#license)

## Getting Started

Since this is an open source project you can contribute with your code and
knowledge, or by making changes to the documentation. We invite and welcome all contributions. Below is a brief
description on how to work with the code and to compile

### Development Workflow

Development happens in the `dev` branch. All Pull-Requests should be
pointed to that branch. Please, make sure you follow the
[CONTRIBUTING.md](CONTRIBUTING.md) guidelines. All Pull-Requests
require that at least two developers review them first before merging to `dev`
branch.

### Installing RIOT-OS

RIOT is a real-time multi-threading operating system that supports a range of devices that are typically found in the Internet of Things (IoT): 8-bit, 16-bit and 32-bit microcontrollers.

### Pre-requisites

1. Install Git.
2. Install the build-essential packet (make, gcc etc.). This varies based on the operating system in use. para `mac` le recomendamos usar `xcode-select install`.
3. Install OpenOCD

### Installation of ESP-IDF (Espressif IoT Development Framework) 

ESP-IDF, the official SDK from Espressif, can be downloaded and installed as GIT repository.

1) cd $HOME/esp
2) git clone https://github.com/espressif/esp-idf.git
3) cd esp-idf
4) git checkout f198339ec09e90666150672884535802304d23ec
5) git submodule init
6) git submodule update

### Install Manual toolchain

The quickest way to start development with ESP32 is by installing a prebuilt toolchain. Below you will be given the installation steps for the toolchain by operating system:

1) [MacOS](https://docs.espressif.com/projects/esp-idf/en/release-v3.0/get-started/macos-setup.html)

2) [Linux](https://docs.espressif.com/projects/esp-idf/en/release-v3.0/get-started/linux-setup.html)

It is recommended that you save the toolchain in the esp folder created earlier.

### Toolchain Usage

Once you have installed all required components, you should have the following directories.
```
/path/to/esp/esp-idf
/path/to/esp/xtensa-esp32-elf
```
To use the toolchain and optionally the SDK, please check that your environment variables are set correctly to

```
export ESP32_SDK_DIR=/path/to/esp/esp-idf
export PATH=$PATH:/path/to/esp/xtensa-esp32-elf/bin
```


### Compiling

To compile an application for an ESP32 board, change to RIOT's root directory and execute the `make` for linux  and  `gmake` for MacOS command.

### Flashing the Firmware

To upload the binary to the ESP32 you have connected to your computer, you
need to use the following command:

```bash
  make -p PORT flash 
```

Where `PORT` specifies on what port you have connected your ESP32 development
board.


### Compiling Documentation

You can compile the code documentation by installing the following tools:

1. [Doxygen](http://www.doxygen.nl/download.html)
2. [Python 3](https://www.python.org/downloads/)
3. `pip install -U sphinx`
4. `pip install -U sphinx-rtd-theme`
5. `pip install -U breathe`

Now you can just checkout to the `doc/` directory and run:

```bash
make html
```

The documentation will reside in `doc/build/_html/`, from there you can open
`index.html`.

## License
Copyright © 2019 **Bitcoin Venezuela** and **Locha Mesh** developers.

Licensed under the **Apache License, Version 2.0**

---
**A text quote is shown below**

>Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
___
Read the full text:
[Locha Mesh Apache License 2.0](LICENSE)
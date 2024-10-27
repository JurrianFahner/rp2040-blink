# rp2040 blink

This is my first project where I used rust to program the [raspberry pi pico](https://www.raspberrypi.com/products/raspberry-pi-pico/).

I used the [rp2040-project-template](https://github.com/rp-rs/rp2040-project-template.git) as a base for this experiment.

## prerequisites and assumptions

- Windows 11 is used as operating system
- Visual studio code is used as IDE
- rustup needs to be installed, to install it please [follow these instructions](https://rustup.rs/) (to avoid license issues make sure to install `x86_64-pc-windows-gnu` target, unless you have a valid visual studio subscription)
- as a shell powershell is used (in windows terminal)

## preparation steps

```powershell
# to update rustup to the latest version
rustup self update

# update local rust installation to the latest stable release channel
rustup update stable

# install extra target to have support for the cortex cpus (included in this target selection are M0, M0+ and M1)
rustup target add thumbv6m-none-eabi

# flip-link is a prerequisite for this project, it adds stack overflow protection
# since bare metal programs loses some safety, due to the fact that the standard library is not used
cargo install flip-link

# for this project we are loading UF2 over usb, so the following program needs also to be installed
cargo install elf2uf2-rs --locked

# clone this project
git clone https://github.com/JurrianFahner/rp2040-blink.git
```

## deploy the blink program

First boot the pico into usb boot loader mode by holding the bootsel button on the board during connecting the board to usb. 

To deploy the blink program, execute the following command:

```powershell
cargo run --release
```

## see below the end result

Click on the image below to watch the result on youtube.
[![end result](https://img.youtube.com/vi/wNA5cxpZF54/0.jpg)](https://www.youtube.com/watch?v=wNA5cxpZF54)
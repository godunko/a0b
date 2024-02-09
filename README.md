# Ada On Board

Main purpose of this project is to create modular architecture to support
development of Ada applications that run on bare boards.

Each module is packaged as Alire crate, thus set of necessary modules can be managed easly.

Each module has its own repository and supported by the particular person/team.

## Available modules

 * [A0B: Base components](https://github.com/godunko/a0b-base)
 * [A0B: ARMv7-M support (Cortex-M3, Cortex-M4, Cortex-M7)](https://github.com/godunko/a0b-armv7m)
 * [A0B: ATSAM3X8E SVD package](https://github.com/godunko/a0b-svd-atsam3x8e)
 * [A0B: STM32F407 SVD package](https://github.com/godunko/a0b-svd-stm32f407)
 * [A0B: STM32H723 SVD package](https://github.com/godunko/a0b-svd-stm32h723)

## Futute ideas

Create startup files and linker scripts for polular boards.

Create HAL (really HAL, not some MCU family centric) for common interfaces (PIO, I2C, SPI) and modules to support them on specific MCU. When necessary, HAL should provide both synchronous and asynchronous API.

Provide support for minimal set of Ada tasking constructs without `light-tasking-*` runtime provided by the GNAT compiler. It might be based on GNAT tasking implementation or on some RTOS.

Provide implementation of asynchronous HAL API on top of Ada tasking.

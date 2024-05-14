# Ada On Board

Main purpose of this project is to create modular architecture to support
development of Ada applications that run on bare boards.

Each module is packaged as Alire crate, thus set of necessary modules can be managed easly. Alire crates are available in [A0B Alire Index](https://github.com/godunko/a0b-alire-index). They will be submited to the [Alire Community Index](https://github.com/alire-project/alire-index) after stabilization.

Each module has its own repository, and packages as single, and sometimes multiple Alire crates.

## Available modules

 * Core components
   * [A0B: Base components](https://github.com/godunko/a0b-base)
   * [A0B: Monotonic Time and Clock](https://github.com/godunko/a0b-time)
   * [A0B: Timer](https://github.com/godunko/a0b-timer)
   * [A0B: Tasking](https://github.com/godunko/a0b-tasking)
 * Architecture support
   * [A0B: ARMv7-M support (Cortex-M3, Cortex-M4, Cortex-M7)](https://github.com/godunko/a0b-armv7m)
 * SVD 
   * [A0B: ATSAM3X8E SVD package](https://github.com/godunko/a0b-svd-atsam3x8e)
   * [A0B: STM32F407 SVD package](https://github.com/godunko/a0b-svd-stm32f407)
   * [A0B: STM32H723 SVD package](https://github.com/godunko/a0b-svd-stm32h723)
 * MPU support
   * ATSAM3X8E (Arduino Due) 
     * [A0B: ATSAM3X8E Base](https://github.com/godunko/a0b-atsam3x8e)
     * [A0B: ATSAM3X8E High Resolution Timer on top of TC5](https://github.com/godunko/a0b-atsam3x8e-tc5_timer)
     * [A0B: ATSAM3X8E GPIO/EXTI](https://github.com/godunko/a0b-atsam3x8e-gpio)
     * [A0B: ATSAM3X8E SPI](https://github.com/godunko/a0b-atsam3x8e-spi)
     * [A0B: ATSAM3X8E USART](https://github.com/godunko/a0b-atsam3x8e-usart)
 * PlayStation Controller driver
   * [Asynchronous neutral layer](https://github.com/godunko/a0b-playstation2_controller-async)
   * [Asynchronous transport layer for STM32F407](https://github.com/godunko/a0b-playstation2_controller-async-stm32f407)

## Futute ideas

Create startup files and linker scripts for polular boards.

Create MPU agnostic interfaces for synchronous and asynchronous drivers of common peripheral controllers (EXTI, SPI, I2C), as well as implementation of the these drivers for particular boards/MPU famalies. 

Provide implementation of asynchronous API on top of Ada tasking.

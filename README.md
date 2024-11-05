# Ada On Board

Main purpose of this project is to create modular architecture to support
development of Ada applications that run on bare boards.

Each module is packaged as Alire crate, thus set of necessary modules can be managed easly. Alire crates are available in [A0B Alire Index](https://github.com/godunko/a0b-alire-index). They will be submited to the [Alire Community Index](https://github.com/alire-project/alire-index) after stabilization.

Each module has its own repository, and packages as single, and sometimes multiple Alire crates.

## Available modules

 * Core components
   * [A0B: Base components](https://github.com/godunko/a0b-base)
   * [A0B: Callbacks](https://github.com/godunko/a0b-callbacks)
   * [A0B: Monotonic Time](https://github.com/godunko/a0b-time)
   * [A0B: Timer](https://github.com/godunko/a0b-timer)
   * [A0B: Tasking](https://github.com/godunko/a0b-tasking)
 * Abstract higher level API
   * [A0B: Abstract EXTI API](https://github.com/godunko/a0b-exti)
   * [A0B: Abstract GPIO API](https://github.com/godunko/a0b-gpio)
   * [A0B: Abstract I2C API](https://github.com/godunko/a0b-i2c)
   * [A0B: Abstract SPI API](https://github.com/godunko/a0b-spi)
 * Architecture support
   * [A0B: ARMv7-M support (Cortex-M3, Cortex-M4, Cortex-M7)](https://github.com/godunko/a0b-armv7m)
 * SVD (obsolete, see base support crates for particular MCU)
   * [A0B: STM32F407 SVD package](https://github.com/godunko/a0b-svd-stm32f407)
 * MCU support
   * ATSAM3X8E 
     * [Base packages and files generated from SVD](https://github.com/godunko/a0b-atsam3x8e)
     * [High Resolution Timer on top of TC5](https://github.com/godunko/a0b-atsam3x8e-tc5_timer)
     * [GPIO/EXTI](https://github.com/godunko/a0b-atsam3x8e-gpio)
     * [SPI](https://github.com/godunko/a0b-atsam3x8e-spi)
     * [USART](https://github.com/godunko/a0b-atsam3x8e-usart)
   * STM32F401
     * [Base packages and files generated from SVD](https://github.com/godunko/a0b-stm32f401)
     * [High resolution timer on top of TIM11](https://github.com/godunko/a0b-stm32f401-tim11_timer)
     * [GPIO/EXTI](https://github.com/godunko/a0b-stm32f401-gpio) driver
     * [DMA](https://github.com/godunko/a0b-stm32f401-dma) support for use by drivers
     * [I2C](https://github.com/godunko/a0b-stm32f401-i2c) driver
     * [USART](https://github.com/godunko/a0b-stm32f401-usart) in UART/SPI mode
   * STM32H723
     * [Base packages and files generated from SVD](https://github.com/godunko/a0b-stm32h723)
     * [GPIO/EXTI](https://github.com/godunko/a0b-stm32h723-gpio)
 * Board support
   * Arduino Due [startup code and linker script](https://github.com/godunko/light-startup) to use with `light-cortex-m3` runtime
   * BlackPill STM32F401 [startup code and linker script](https://github.com/godunko/light-startup) to use with `light-cortex-m4f` runtime
   * STM32F407 Discovery [startup code and linker script](https://github.com/godunko/light-startup) to use with `light-cortex-m4f` runtime
   * FK723M1-ZGT6 [startup code and linker script](https://github.com/godunko/light-startup) to use with `light-cortex-m7df` runtime
 * Various drivers
   * PlayStation2 Controller driver
     * Platform independent [asynchronous driver](https://github.com/godunko/a0b-playstation2_controller) builds on top of A0B's neutral EXTI/SPI/Timer API
     * [Asynchronous neutral layer](https://github.com/godunko/a0b-playstation2_controller-async)
     * [Asynchronous transport layer for STM32F407](https://github.com/godunko/a0b-playstation2_controller-async-stm32f407)
   * [PCA9685 PWM driver](https://github.com/godunko/a0b-pca9685)
   * [MPU6050/6500/9150/9250 IMU driver](https://github.com/godunko/a0b-mpuxxxx)

## Examples

[Examples](https://github.com/godunko/a0b-examples) repository provides few examples:
  * Remote control of position of servo motor, it utilize PlayStation2 Controller as remote controller and PCA9685 board for servo motor control
  * MPU9250 IMU calibration utility, it can be used to calibrate accelerometer and gyroscope of the sensor

## Futute ideas

Create startup files and linker scripts for popular boards.

Create MCU agnostic interfaces for synchronous and asynchronous drivers of common peripheral controllers (EXTI, SPI, I2C), as well as implementation of the these drivers for particular boards/MCU famalies. 

Provide implementation of asynchronous API on top of Ada tasking.

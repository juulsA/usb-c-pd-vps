# USB-C-PD-VPS

- variable powersupply driven by USB-PD 
- modular, up to 4 channels
- each channel is isolated
- output voltage 0 - 32V
  - resolution 0.5mV/step
  - voltage correction via sensing pins up to 1V above internally set output voltage
- current sense
  - "fuse" mode
  - current limiting mode
- remote control via USB

## Power Supply Channel Concept
![power-supply-channel-design](/images/pwr_spl_concept.png)

## STM32 Pinout

| Pin Number | Pin Name | Net Name | Description |
| -------- | ------- | ------- | ------- |
| 1 | PB9 | - | - |
| 2 | PC14 | OSCX_IN | - |
| 3 | PC14 | OSCX_OUT | - |
| 4 | VDD | - | - |
| 5 | VSS | - | - |
| 6 | PF2 | NRST | hardware reset |
| 7  | PA0 | ADC0 | secondary side voltage monitoring |
| 8 | PA1 | - | - |
| 9 | PA2 | - | - |
| 10 | PA3 | ADC_SPI_NSS | adc chip select |
| 11 | PA4 | DAC_SPI_NSS | dac chip select |
| 12 | PA5 | STM32_SPI_SCK | spi clock |
| 13 | PA6 | STM32_SPI_MISO | master input/slave output |
| 14 | PA7 | STM32_SPI_MOSI | master output/slave input |
| 15 | PB0 | - | -|
| 16 | PB1 | - | -|
| 17 | PB2 | - | - |
| 18 | PA8 | - | - |
| 19 | PA9 | STM32_UART_TX | uart for controlling/programming |
| 20 | PC6 | - | - |
| 21 | PA10 | STM32_UART_RX | uart for controlling/programming |
| 22 | PA11 | - | - |
| 23 | PA12 | - | - |
| 24 | PA13 | SWDIO | - |
| 25 | PA14 | SWCLK/BOOT0 | enable stm bootloader |
| 26 | PA15 | STM32_TIM1_CH1_PWM | setting preregulator voltage |
| 27 | PB3 | DISABLE_VOLTAGE_SENSING | the external sense pins are not considered in output voltage adjustment  |
| 28 | PB4 | FUSE/#CURRENT_LIMITING_MODE | output is disabled, if an overcurrent event occurs or current is limited by reducing output voltage |
| 29 | PB5 | FPWM/#PFM | fixed frequency or phase frequency mode |
| 30 | PB6 | ENABLE_PWR_SPL | enable switching regulator |
| 31 | PB7 | PG | power good of switching regulator |
| 32 | PB8 | ENABLE_OUTPUT | voltage is applied to the output pins |
# SPI_Keil
## Hardware
This firmware developed on STM32F4Discovery board: [link](https://www.st.com/en/evaluation-tools/stm32f4discovery.html). The SPI device in test is on-board three-axis "nano" accelerometer, [LIS3DSH](https://www.st.com/content/ccc/resource/technical/document/application_note/a6/78/86/f9/88/c0/49/9b/DM00026768.pdf/files/DM00026768.pdf/jcr:content/translations/en.DM00026768.pdf). The accelerometer has a configurable output rate, measurement range, enable/disable separate axis, Data ready flag, and etc. 

## Software
Code based on CubeMX to initailize SPI interface and External interrupt pin.

The accelerometer is set to read all 3 axis, output rate at 12.5 Hz with Data ready flag. The firmware is interrupt driven using the data ready flag from the accelero meter. Once interrupt function called, the SPI will read in 6 bytes of data (2 byte for each axis) in uint8_t data type then convert 2 byte of uint8_t into 1 int16_t (result_x, result_y, result_z) accordingly.

This code has been tested using STMStudio to plot the result_x, result_y, result_z output.

## Reference
https://www.youtube.com/watch?v=rg25-zU3R-E

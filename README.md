# SSD1306 libopencm3

Library to use any SSD1306 OLED display with STM32 using [libopencm3](https://github.com/libopencm3/libopencm3). \
Supports STM32F1 and STM32F4. Feel free to modify the code for your specific board, and don't forget to submit a PR for any improvements.

### Getting started
1. Modify `ssd1306_conf.h` to suit your needs. The current code works with SPI1 and STM32F1.

2. After initializing SPI/I2C and pins, the code is very straightforward:

```c
	#include "ssd1306.h"
	#include "ssd1306_fonts.h"
	
	void periphInit(){ 
		// initialize the peripherals and pins (see examples folder)
	}
	
	int main(){
		periphInit();
		
		ssd1306.Init(); // Send commands 
		ssd1306.SetCursor(30,30);
		ssd1306.WriteString("Hello, World!", Font_7x10, White);
		ssd1306.UpdateScreen();
		
		while(1){
			// loop code
		}
		return 0;
	}

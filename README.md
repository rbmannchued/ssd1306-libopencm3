# SSD1306 libopencm3

Library to use any ssd1306 oled display with stm32 using [libopencm3](https://github.com/libopencm3/libopencm3). 
Tested on STM32f1x and 128x64 oled for now.
### Getting started
1. Change 'ssd1306_conf.h' to your needs, the actual code work with SPI1 and STM32f1.


2. After initializing SPI/I2c and pins the code is very straight foward:

```c
	#include <ssd1306.h>
	#include <ssd1306_fonts.h>
	
	void periphInit(){ 
		//initialize the peripherals and pins (see example)
	}
	
	int main(){
		periphInit();
		
		ssd1306.Init(); //Send commands 
		ssd1306.SetCursor(30,30);
		ssd1306.WriteString("Hello, World!",Font_7x10,White);
		ssd1306.UpdateScreen();
		
		while(1){
			//loop code
		}
		return 0;
	}
```
	
 Code based on [stm32-ssd1306](https://github.com/afiskon/stm32-ssd1306).

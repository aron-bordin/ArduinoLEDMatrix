# Led Matrix

#IMPORTANT
### This library was moved to a new repository: https://github.com/aron-bordin/PNG-Arduino-Framework
I'll update just the new repository. Check and star the .PNG Arduino Framework, there are more objects and Arduino components. This new repository has a better documentation.

This is a helper class to work with [16x16 LED Matrix with Arduino](http://www.elabpeers.com/led-matrix-display.html).

You can read the full tutorial here: https://bytedebugger.wordpress.com/2015/01/28/tutorial-how-to-use-dot-led-matrix-display-with-arduino/

# Example
```c++

	#include "LedMatrixObject.h"


	LedMatrixObject *led = new LedMatrixObject(2, 3, 4, 5, 6, 7, 8, 9);

	unsigned char  Scene[16][16] = {
	    {1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1},
	    {1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1},
	    {1, 1, 0, 1, 1, 1, 0, 1, 1, 1, 0, 1, 1, 1, 1, 1},
	    {1, 1, 0, 1, 1, 1, 0, 1, 1, 1, 0, 1, 1, 1, 1, 1},
	    {1, 1, 0, 1, 1, 1, 0, 1, 1, 1, 0, 1, 1, 0, 1, 1},
	    {1, 1, 0, 1, 1, 1, 0, 1, 1, 1, 0, 1, 1, 0, 1, 1},
	    {1, 1, 0, 1, 1, 1, 0, 1, 1, 1, 0, 1, 1, 0, 1, 1},
	    {1, 1, 0, 1, 1, 1, 0, 1, 1, 1, 0, 1, 1, 0, 1, 1},
	    {1, 1, 0, 0, 0, 0, 0, 1, 1, 1, 0, 1, 1, 0, 1, 1},
	    {1, 1, 0, 1, 1, 1, 0, 1, 1, 1, 0, 1, 1, 0, 1, 1},
	    {1, 1, 0, 1, 1, 1, 0, 1, 1, 1, 0, 1, 1, 0, 1, 1},
	    {1, 1, 0, 1, 1, 1, 0, 1, 1, 1, 0, 1, 1, 1, 1, 1},
	    {1, 1, 0, 1, 1, 1, 0, 1, 1, 1, 0, 1, 1, 1, 1, 1},
	    {1, 1, 0, 1, 1, 1, 0, 1, 1, 1, 0, 1, 1, 0, 1, 1},
	    {1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1},
	    {1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1},
	};

	void setup(){

	}

	void loop(){
		led->setScene(Scene);
		led->setLedOn(0, 0);
		led->setLedOff(8, 5);
		led->draw();
	}
```

# Documentation

**LedMatrixObject(byte LEDARRAY_D, byte LEDARRAY_C, byte LEDARRAY_B, byte LEDARRAY_A, byte LEDARRAY_G, byte LEDARRAY_DI, byte LEDARRAY_CLK, byte LEDARRAY_LAT);** - Create the LED matrix

**void clear();** - clear the scene

**void draw();** - draw the scene on the led matrix - call it on loop()

**void setScene(unsigned char  Scene[16][16]);** - set and Scene[16][16]

**void setLedOn(int x, int y);** - Turn on the led x, y on

**void setLedOff(int x, int y);** -  Turn off the led x,y

**void toggleLed(int x, int y);** -  Toggle the state of the led x,y

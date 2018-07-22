VGA stands for Video graphics array and it’s one of the most diffuse standard for video transmission; it roots its definition from the way old catodic tubes work: the image is constructed one lines at times, starting from the top and each line is displayed from the left to the right (by the way this is the reason for the Y axes orientation in graphics programming); physically this is done by an electron beam guided from some electromagnets internal to the screen that hit the pixels (?).

Following this scheme is easy enough imagine that the signals of this interface are the following

Signal	Logic level	Description
VSYNC	5V	Tells the monitor when a screen has been completed
HSYNC	5V	Tells the monitor that a line has been completed
R	0.7V	red color channel
G	0.7V	green color channel
B	0.7V	blue color channel
To be a little more clear, below a time diagram stolen from this page that implements a similar concept in VHDL.

The front porch and back porch are safety timing around the sync pulse (I think) to allow the old circuitery to have time to move the beam. During these periods the beam is not in condition to generate images.

These signals can vary a lot based on resolution/refresh time of the screen, but in my case I choosen to stick with the pretty standard 640x480@60Hz.

With this resolution I’ll use the following value in pixel clock for the front, back porch and sync pulse
         front	  sync	back
HSYNC  	16pc    	96pc	48pc
VSYNC	  10pc	    2pc	  33pc





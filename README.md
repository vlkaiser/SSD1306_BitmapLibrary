# Bitmap Library
Developed on STM32 NUCLEO-F072RB in STM32CubeIDE for use with [Stm32-ssd1306 library](https://github.com/vlkaiser/stm32-ssd1306)

(Read: Not for Arduinos)

This is a (hacky) lightweight library intended to draw bitmap images on a (0.96") OLED display.


## How to Use
### My Setup
- STM32CubeIDE 
- stm32-ssd1306 OLED driver chip library for the STM32FX family.  
- STM32 NUCLEO-F072RB (But nearly any STM32FX will work - config in ssf1306_conf.h)
- 128x64 0.96" OLED display eg HiLetGo 3-01-1234-IIC-W or Adafruit 326
- Follow the OLED_I2C Readme instructions to add/link the libraries to the project.

### Convert your image
- Scale your desired image to no larger than 128x64 (display size) 

- Convert the image to a bitmap   
eg [image2CPP](https://diyusthad.com/image2cpp)  
I used the parameters: BLACK Background, INVERT Image colors, HORIZONTAL Draw Mode  but adjust as necessary for your desired look
- Note the Width and Height values of the image.

### Add "Image" to Project
I guess make a copy of my Logo "_static const unsigned char_".  Give it a unique name, and then fill in your own bitmap (that's the hex values).
**If your conversion program doesn't put commas at the end of each row, you will need to.**  
- Give a unique variable name to the Width and Height variables and populate them with the Width/Height values from the conversion program.

### Call drawBitmap
- Read the header, it explains what each of the parameters are.  Starting (x, y), your bitmap name (the _static const unsigned char_ from above), the Width and Height defined above, and then what color you want the pixels vs the background to be.     
**Hint:** it's a monochrome display, so you get _Black_ or _White_.

## Disclaimer
I don't really know what I'm doing - I'm by no means an experienced progammer or git user - so forgive my... whatever I'm doing wrong. If you would be so kind as to take some time to educate me on my lack of finess I'd be just thrilled.

This seems to work and I get a nice picture.  No promises that it's "universal" or "optimized"or  anything, but I'm more than happy to take suggestions.

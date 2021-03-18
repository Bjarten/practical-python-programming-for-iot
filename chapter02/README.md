# Chapter 2 - Introduction to Python and IoT

## Virtual environment set up for this chapter<br>
> `$ python3 -m venv venv`<br>
> `$ source venv/bin/activate`<br>
> `(venv) $ pip install pip --upgrade`<br>
> `(venv) $ pip install -r requirements.txt` 

## Files

* `requirements.txt` - Python dependencies required for this chapter

* `led_gpiozero.py` - Flashing a LED using GPIOZero

* `led_pigpio.py` - Flashing a LED using PiGPIO

* `button_gpiozero.py` - Responding to a button using GPIOZero

* `button_pigpio.py` - Responding to a button using PiGPIO

* `dweet_led.py` - Controlling a LED over the Internet using dweet.io

* `dweet_button.py` - Creating a dweet using a push button

* `pigpio_led_class.py` - PiGPIO class wrapper example

## Resources
* [Dwwet.io](http://dweet.io/) - Simple publishing and subscribing for machines, sensors, devices, robots, and gadgets.
* [GPIOZero](https://gpiozero.readthedocs.io/en/stable/) - High level library
* [PiGIO](http://abyz.me.uk/rpi/pigpio/python.html) - Low level library

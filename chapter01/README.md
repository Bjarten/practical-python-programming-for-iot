# Chapter 1 - Setting Up Your Development Environment 

## Setting up a Python virtual environment
#### Create a virtual environment
```$ python3 -m venv venv```

#### Activate the virtual environment
```$ source venv/bin/activate```

#### Deactivate the virtual environment
```(venv) $ deactivate```

#### Check the location of the Python executable
```(venv) $ which python```<br>
When the virtual environment is activate it should look something
like this: ```/home/pi/venv/bin/python```. The path can be different
depending on where you create the environment.

#### List installed ```pip``` packages
```(venv) $ pip list```

#### Save a requirements.tx file
```(venv) $ pip freeze > requirements.txt```

#### Install packages using the requirements.txt file
```(venv) $ pip install -r requirements.txt```

#### Some basic `pip` commands

```
# Remove a package
(venv) $ pip uninstall <package name>
# Search for a package
(venv) $ pip search <query text>
# See all pip commands
(venv) $ pip --help
```

## Virtual environment set up for this chapter<br>
### Option 1
1. `$ python3 -m venv venv`
2. `$ source venv/bin/activate`
3. `(venv) $ pip install pip --upgrade`
4. `(venv) $pip install -r requirements.txt`

### Option 2
1. `$ python3 -m venv venv`
2. `$ source venv/bin/activate`
3. `(venv) $ pip install --upgrade pi`
4. `(venv) $ pip install gpiozero pigpio`
5. `(venv) $ pip freeze > requirements.txt`

## Using sudo within virtual environments
The `sudo` action will use default Python that's available to the root user. The correct way to run a script is to pass the absolute path using the `which python`command:<br>
```
(venv) $ which python
/home/pi/practical-python-programming-for-iot/chapter01/venv/bin/python
```
To run a script using the virtual environment Python interpreter, use `sudo` with its absolute path:<br>
```
(venv) $ sudo /home/pi/practical-python-programming-for-iot/chapter01/venv/bin/python my_script.py
```
## Executing Python scripts outside of their virtual environments
To run scripts with the virtual environments Python interpeter without activating the environment itself:<br>
```
/home/pi/practical-python-programming-for-iot/chapter01/venv/bin/python my_script.py
```
Or with `sudo`:<br>
```
sudo /home/pi/practical-python-programming-for-iot/chapter01/venv/bin/python my_script.py
```
Since we are using the virtual environments Python interpeter, we are using all its packages, jsut like if we would if we had activated the environment.

## Running a Python script at boot
Here is an example on how to run a Python script automatically on boot using a feature of `cron`, the Unix scheduler.<br>

Here are the stpes to configure cron and run the script on boot:<br>
1. In the project forlder, create a bash script. E.g. `run_on_boot.sh`:
>```#!/bin/bash
>
># Absolute path to virtual environment  python interpeter
>PYTHON=/home/pi/practical-python-programming-for-iot/chapter01/venv/bin/python
>
># Absolute path to Python script
>SCRIPT=/home/pi/practical-python-programming-for-iot/chapter01/gpio_pkg_check.py
>
># Absolute path to output log file
>LOG=/home/pi/practical-python-programming-for-iot/chapter01/gpio_pkg_check.log
>
>echo -e "\n####### STARTUP $(date) #######\n" >> $LOG
>$PYTHON $SCRIPT >> $LOG 2>&1
This bash script will run the script using the virtual environment Python interpeter, and log the output of the script. The `2>&1` is necessary for errors to be logged.

2. Make `run_on_boot.sh`executable.
>`$ chmod u+x run_on_boot.sh`
3. Edit the `crontab` file, which is the file where cron scheduling rukes are stored:
>`$ crontab -e`
4. Add the following entery to the `crontab` file, using the absolute path to the `run_on_boot.sh`:
> @reboot /home/pi/practical-python-programming-for-iot/chapter01/run_on_boot.sh &
The `&`character makes sure the script runs in the background.
5. Run `run_on_boot.sh` in a terminal to make sure that it works. Check the `gpio_pkg_check.log`, it should look like this:
>```
> $ ./run_on_boot.sh
> $ cat gpio_pkg_check.log
> ####### STARTUP Tue 09 Mar 2021 08:37:12 AM CET ######
>
>GPIOZero   Available
>PiGPIO     Available
>```
6. Reboot the Raspberry Pi:
> `sudo reboot`
7. When booted up again, check the `gpio_pkg_check.log`file, it should contain additional lines:

>```
>####### STARTUP Tue 09 Mar 2021 08:37:12 AM CET ######
>
>GPIOZero   Available
>PiGPIO     Available
>
>####### STARTUP Tue 09 Mar 2021 08:42:46 AM CET ######
>
>GPIOZero   Available
>PiGPIO     Available```

## Configure the PiGPIO daemon
To be able to use the PiGPIO client library we need to start the PiGPIO daemon. The following commands will ensure that the PiGPIO daemon starts automatically at boot.
>`$ sudo systemctl enable pigpiod`<br>
>`$ sudo systemctl start pigpiod`

## Files
* `requirements.txt` - Python dependencies required for this chapter

* `gpio_pkg_check.py` - Verify availability of Python GPIO Libraries 

* `run_on_boot.sh` - Bash helper script to start a Python program on boot 

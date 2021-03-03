# Chapter 1 - Setting Up Your Development Environment 

## Notes
### Setting up a Python virtual environment
#### Create a virtual environment
```$python3 -m venv venv_name```

#### Activate the virtual environment
```$source venv_name/bin/activate```

#### Deactivate the virtual environment
```$deactivate```

#### Check the location of the Python executable
```$which python```<br>
When the virtual environment is activate it should look something
like this: ```/home/pi/venv_name/bin/python```. The path can be different
depending on where you create the environment.

#### List installed ```pip``` packages
```$pip list```

#### Save a requirements.tx file
```$pip freeze > requirements.txt```

#### Install packages using the requirements.txt file
```$pip install -r requirements.txt```

#### Some basic `pip` commands

```
# Remove a package
$pip uninstall <package name>
# Search for a package
$pip search <query text>
# See all pip commands
$pip --help
```

## Set up for the virtual environment for this chapter<br>
### Option 1
1. ```$source venv_name/bin/activate```
2. ```$pip install -r requirements.txt```

### Option 2
1. ```$source venv_name/bin/activate```
2. ```$pip install --upgrade pi```
3. ```$pip install gpiozero pigpio```
4. ```$pip freeze > requirements.txt```

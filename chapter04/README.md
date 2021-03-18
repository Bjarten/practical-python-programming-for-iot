# Chapter 4 - Distributed Systems with Python and MQTT

## Virtual environment set up for this chapter<br>
> `$ python3 -m venv venv`<br>
> `$ source venv/bin/activate`<br>
> `(venv) $ pip install pip --upgrade`<br>
> `(venv) $ pip install -r requirements.txt`

## Files

* `requirements.txt` - Python dependencies required for this chapter

* `mqtt_led.py` - Paho MQTT Pub/Sub example to control a LED

* `mosquitto_pyiot.conf` - Mosquitto MQTT Broker configuration file to enable Web Sockets and Web Server

* `mosquitto_www` - Folder containing HTML and JavaScript files for MQTT Web Page client

* `mosquitto_www/index.html` - MQTT Web Page Client to control LED

* `mosquitto_www/*.js` - JavaScript dependencies as used in index.html

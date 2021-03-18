# Chapter 3 - RESTFul APIs and Web Socket Services with Flask

## cURL
We can use the `curl` command-line tool to interacte with Flask API.

### Example commands
Get the current led brightness value
> `$ curl -X GET http://localhost:5000/led`

Set the new value for led brightness
> `$ curl -X POST -d '{"level": 100}' -H "Content-Type: application/json" http://localhost:5000/led`

### cURL options for GET
`curl -X GET [options] [URL]`
* `-X GET`: The HTTP request method that will be used when communicationg with the remote server
* `URL`: The URL to request

### cURL options for POST
`curl -X POST [options] [URL]`
* `-X POST`: The HTTP request method that will be used when communicationg with the remote server
* `-d`: This is the data we want to POST to the server, in our case it is in json format
* `-H`: To set a specific header or Content-Type. 
In our example we are setting POST request type to `application/json`, to let our server know that the data we are sending is a JSON object
* `URL`: The URL to request

## Virtual environment set up for this chapter<br>
> `$ python3 -m venv venv`<br>
> `$ source venv/bin/activate`<br>
> `(venv) $ pip install pip --upgrade`<br>
> `(venv) $ pip install -r requirements.txt`

## Files

* `requirements.txt` - Python dependencies required for this chapter

* `flask_api_server.py` - RESTful API Server to control a LED

* `flask_ws_server.py` - Web Socket Server API server to control a LED

* `templates/index_api_client.html` - Web client for `flask_api_server.py`

* `templates/index_ws_client.html` - Web client for `flask_ws_server.py`

* `static/jquery.min.js` - JQuery JavaScript library for both web clients

* `static/socket.io` - Socket.io JavaScript library for `index_ws_client.html`

## Resources
* [localtunnel.github.io](https://localtunnel.github.io/) - Localtunnel allows you to easily share a web service on your local development machine without messing with DNS and firewall settings.
* [ngrok.com](https://ngrok.com/) - Spend more time programming. One command for an instant, secure URL to your localhost server through any NAT or firewall.
* [REST on SitePoint.com](https://www.sitepoint.com/developers-rest-api/)
* [Flask Quick Start](https://flask.palletsprojects.com/en/1.1.x/quickstart/)
* [Flask-RESTful Quick Start](https://flask-restful.readthedocs.io/en/latest/quickstart.html)
* [Flask documentation](https://flask.palletsprojects.com/)
* [Flask-SocketIO](https://flask-socketio.readthedocs.io/en/latest/)
* [Socket.IO (javascript library)](https://socket.io/)
* [Web Socket basics](https://www.html5rocks.com/en/tutorials/websockets/basics/) - HTML5 Rocks article
* [Web Socket basics](https://medium.com/@td0m/what-are-web-sockets-what-about-rest-apis-b9c15fd72aac) - Medium article
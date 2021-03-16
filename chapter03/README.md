# Chapter 3 - RESTFul APIs and Web Socket Services with Flask

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

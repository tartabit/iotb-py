# iotb-py


This package provides some useful scripts for interacting with the Tartabit IoT Bridge from Python.  

It implements the REST API that is available here: https://bridge-us.tartabit.com/swaggerui/

This package is expected to change frequently, and may be replaced by a formal python SDK in the future.

## Using the client
```python

from client import IotbClient

# authenticating with an application token
client = IotbClient("https://bridge-us.tartabit.com/api/v1/", token="AT:adfasdf....asdfasd")

# authenticating with a username and password
client = IotbClient("https://bridge-us.tartabit.com/api/v1/", username="user@domain.com", password="password")

resp = client.request("GET", "log", query={"limit": 20})
```

## Utilities
### download-logs.py
This utility downloads application logs from an instance of the IoT Bridge and saves them to a JSON file.
```bash
python download-logs.py -u "https://bridge-us.tartabit.com/api/v1" -t "AT:xxxx" -d 30 -q "level == \"warn\""
```
* -u: The URL used to access the IoT Bridge API.
* -t: The application token used to authenticate with the IoT Bridge.
* -d: The number of days of logs to download.
* -q: A query string used to filter the logs.  Quotes must be escaped with \'\\'.

## License

Mozilla Public License Version 2.0

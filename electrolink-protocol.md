## Function List

| SUBSYS              | FNC                                                 |
|:--------------------|:----------------------------------------------------|
| SYSTEM              | **ping**()                                          |
|                     | **getInfo**()                                       |
|                     | **getCallbacks**()                                  |
|                     | **reset**()                                         |
|                     | **setAckReceipt**(boolean value)                    |
| USER                | **methodName([data array])                          |


### ping()

This is ping function, it returns 1 if executed. It's used to check if device is connected and responding in the network.


Request JSON:
```
{
  "method": "ping",
  "params": []
}
```

Return JSON:
```
{
  "requested":"ping",
  "params":[], 
  "value":1
}
```

### getInfo()

This function will return information about device in form of dictionary.

Request JSON:
```
{
  "method": "getInfo",
  "params": []
}
```

Return JSON:
```
{
  "requested":"getInfo",
  "params":[], 
  "value": {
              "board": "ESP8266",
              "name": "miniWeIO",
              "command": "miniWeIO/command"
              "reply": "miniWeIO/reply"
              "error": "miniWeIO/error"
              "console": "miniWeIO/console"
              "version": "1.0"
            }
}
```

Return values:

"board"   - hardware board type
"name"    - name of device
"command" - command channel topic
"reply"   - reply channel topic where device will push answers
"error"   - error channel topic where device will push errors
"console" - console channel topic where console sends commands
"version" - firmware version

### reset()

Resets electronics. 

Request JSON:
```
{
  "method": "reset",
  "params": []
}
```
No return message.

### setAckReceipt()

Sets Avis de Reception parameter. If setAckReceipt is set to true than all called functions has to give an answer. If function don't have answer then returned value will be "OK"

Request JSON:
```
{
  "method": "setAckReceipt",
  "params": [true]
}
```

Return JSON:
```
{
  "requested": "setAckReceipt",
  "params": [true],
  "value": "OK"
}
```


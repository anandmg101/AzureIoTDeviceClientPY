# Azure IoT DeviceClient for Python

```python
import DeviceClient


# START: Azure IoT Hub settings
KEY = "xxxxx";
HUB = "xxxxx";
DEVICE_NAME = "xxxxx";
# END: Azure IoT Hub settings

device = DeviceClient.DeviceClient(HUB, DEVICE_NAME, KEY)

device.create_sas(600)

# Device to Cloud
print(device.send(b"{message: 'Hello from Python'}"))

# Cloud to Device
message = device.read_message()
print(message['body'])

device.complete_message(message['etag'])
```

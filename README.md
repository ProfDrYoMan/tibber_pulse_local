# Tibber Pulse Local

A knowledge base for tibber pulse local setup.

**WIP**: Targetting local use with mirror to tibber.

## FW State

Based on:

* version: #f95e523
* esp: 1268-f95e5239
* efr: 557-dee09095
* node_version: 986-49df5891

## Frontend URLs

* <http://tibber_bridge/>
  * Bridge info
* <http://tibber_bridge/params/>
  * Bridge parameters
* <http://tibber_bridge/nodes/>
  * Nodes info
* <http://tibber_bridge/nodes/1/data>
  * Data from node 1
* <http://tibber_bridge/nodes/1/metrics>
  * Metrics from node 1
* <http://tibber_bridge/nodes/1/params>
  * Parameters for node 1
* <http://tibber_bridge/nodes/1/config>
  * Meter type configuration for node 1
* <http://tibber_bridge/console/>
  * Command line console
* <http://tibber_bridge/ota/>
  * Over the air update
* <http://tibber_bridge/spiffs/>
  * File system access

## JSON URLs

* <http://tibber_bridge/status.json>
  * Bridge info
* <http://tibber_bridge/params.json>
  * Bridge params
* <http://tibber_bridge/nodes.json>
  * Nodes info
* <http://tibber_bridge/pairing_status.json>
  * Pairing status
* <http://tibber_bridge/ota_manifest.json>
  * OTA manifest
* <http://tibber_bridge/data.json?node_id=1>
  * Data from node 1
* <http://tibber_bridge/metrics.json?node_id=1>
  * Metrics for node 1
* <http://tibber_bridge/node_params.json?node_id=1>
  * Parameters for node 1

## Always Enabling the Web Frontend

To enable the web frontend continuously one variable needs to be set in the web frontend.
But to get into the web frontend for the first time the following steps need to be done:

* Unplug the tibber bridge.
* After three seconds, plug the tibber bridge.
* After three seconds, unplug the tibber bridge.
* After three seconds, plug the tibber bridge.

The LED on the tibber bridge should now light up green and not light blue anymore.

Now use any device (laptop, pad, phone) to connect to the WiFi network ```Tibber Bridge```.
The password is the nine characters printed on the tibber bridge.

Use a web browser on that device to connect to <http://10.133.70.1/>.

The username is ```admin``` and the password is again the nine characters printed on the tibber bridge.

When connected, select the param tab an there find and set the variable ```webserver_force_enable``` to ```true```.

After setting and saving the value, remember to press *"Store params to flash"* on the bottom of the page.

Unplug the tibber bridge, wait ten seconds and plug it back again. Now it should connect back to tibber and the LED should light up light blue.

The web frontend should now be accessible on <http://tibber_bridge/>.

## Home Assistant Config Files Tree

```text
/share/mosquitto
   /tibber_ssl
     /ca.crt
     /cert.crt
     /priv.key
   /tibber_bridge.conf
```

## Home Assistant Config Files

### ca.crt

Content of the file is the value of the variable in <http://tibber_bridge/params.json?node_id=1> named ```ca_cert```.

### cert.ctr

Content of the file is the value of the variable in <http://tibber_bridge/params.json?node_id=1> named ```certificate```.

### priv.key

Content of the file is the value of the variable in <http://tibber_bridge/params.json?node_id=1> named ```private_key```.

### tibber_bridge.conf

Check the file with the same name in this repository. Replace ```[PulseID]``` with the PulseID as extracted below. 

Check the parameter named ```mqtt_topic_sub``` in <http://tibber_bridge/params.json?node_id=1>.

Find the PulseID in the value: ```tibber-bridge/[PulseID]/receive```

## References

* <https://github.com/MSkjel/LocalPulse2Tibber>

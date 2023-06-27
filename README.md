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

* /
  * Bridge info
* /params/
  * Bridge parameters
* /nodes/
  * Nodes info
* /nodes/x/data
  * Data from node x
* /nodes/x/metrics
  * Metrics from node x
* /nodes/x/params
  * Parameters for node x
* /nodes/x/config
  * Meter type configuration for node x
* /console/
  * Command line console
* /ota/
  * Over the air update
* /spiffs/
  * File system access

# JSON URLs

* /status.json
  * Bridge info
* /params.json
  * Bridge params
* /nodes.json
  * Nodes info
* /pairing_status.json
  * Pairing status
* /ota_manifest.json
  * OTA manifest
* /data.json?node_id=x
  * Data from node x
* /metrics.json?node_id=x
  * Metrics for node x
* /node_params.json?node_id=x
  * Parameters for node x

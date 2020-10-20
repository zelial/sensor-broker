# sensor-broker

Sensor-broker is a middleman between MCU sensors themselves and frontends (Prometheus/Grafana, HomeAssistant,...).

It is needed because Prometheus works in pull model when it itself tries to contact monitored systems (sensors) but my sensors spend most time in deep sleep to save battery. 

Sensor-broker is always running so sensors can push data to it (via HTTP GET) and prometheus can pull from it. It also pushes data to MQTT broker on behalf of the sensors so the sensors can have only single upload method (again, saving run time and thus battery).

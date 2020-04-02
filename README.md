# Metrics Demo

This scenario adds support for metrics use cases to the LogStream demo. We open a metrics input on dogstatsd and graphite protocols. We add pipelines for processing that data. We add pipelines for processing weblog data, aggregating it into metric events and then outputting to Influxdb. This scenario also adds InfluxDB as a datastore and Grafana as a visualization engine.

## Notable URLs

| Description                | URL                                                                                                    | Username | Password  |
|----------------------------|--------------------------------------------------------------------------------------------------------|----------|-----------|
| Cribl                      | http://localhost:9000                                                                                  | admin    | cribldemo |
| Grafana                    | http://localhost:8200                                                                                  | admin    | cribldemo |


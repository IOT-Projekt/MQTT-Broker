# MQTT Broker with Mosquitto

This project sets up an MQTT broker using Mosquitto within a Docker container. The broker is configured to run with the latest version of Mosquitto, with persistent data storage and logging.

## Services

The Docker service configuration for Mosquitto includes:

- **Mosquitto Container**: Runs the Eclipse Mosquitto broker.
- **Volumes**: Config, data, and log directories are mounted from the local system for persistence.

## Docker Compose Configuration

```yaml
services:
  mosquitto:
    image: eclipse-mosquitto:latest
    container_name: mosquitto
    network_mode: "host"
    volumes:
      - ./conf:/mosquitto/config
      - ./data:/mosquitto/data
      - ./log:/mosquitto/log

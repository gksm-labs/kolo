# Kolo Telemetry System

A telemetry and dashboard system designed for vehicle ("kolo") monitoring. The project is split into two main components: `whub` and `wall`.

## Components

### 1. Whub (Wireless Hub)
Located in the `whub/` directory.
This component acts as the data collection hub. It uses Bluetooth Low Energy (BLE) to connect to sensors, processes the raw telemetry data, and broadcasts it over the network. 

**Key Features:**
- BLE sensor connectivity
- Real-time data processing
- Network broadcasting to the dashboard

### 2. Wall (Telemetry Dashboard)
Located in the `wall/` directory.
This is the visual frontend of the system. It receives the real-time telemetry data broadcasted by the hub and displays it on a live dashboard. 

**Key Features:**
- Live graphing of speed and acceleration using `matplotlib`
- Displays current distance, revolutions, and maximum speed
- Session management: records data into CSV files with custom suffix names and timestamps
- Interactive GUI: ability to start new recording sessions seamlessly (via the 'New Session' button or 'r' key)

## Setup & Running
*(Note: Both components are built with Python and use standard packaging like `pyproject.toml`)*

To run either component, you will likely need to install their dependencies via your preferred Python package manager (like `poetry` or `pip`).

```bash
cd wall
python -m wall
```

## Data Storage
The dashboard (`wall`) automatically saves session data into CSV files in the `wall/data/` directory. Each session file is timestamped and can optionally be given a custom suffix via the dashboard UI for easier identification.

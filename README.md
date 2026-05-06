# Tethered Jackal Communication Stack

ROS-based communication package for a tethered robotics system integrating a Clearpath Jackal UGV, drone subsystem, and winch controller using CAN bus and serial communication.

The project was developed for communication and coordination between a ground robot and external tethered systems.

## Features
CAN bus communication between Jackal and external systems<br>
Drone pose transmission and reconstruction<br>
Serial communication with embedded controllers<br>
TF and AMCL-based localization extraction<br>
ROS launch integration<br>
Real-time data publishing<br>

## Repo Structure

```
--
jackal_ws/
├── src/
|   ├── maps/
│   └── communication/
│       ├── launch/
│       │   ├── bringup_can.launch
│       │   └── can_comm.launch
│       │
│       ├── src/
│       │   ├── can_publisher.py
│       │   ├── can_publisher_old.py
│       │   ├── can_subscriber.py
│       │   ├── publish_data.py
│       │   └── test_serial.py
│       │
│       ├── CMakeLists.txt
│       └── package.xml
│
├── README.md
└── .gitignore
--
```

## Main Components

can_publisher.py: Publishes robot pose and velocity data over CAN bus using ROS topics.<br>
can_subscriber.py: Receives CAN frames and reconstructs drone pose data.<br>
publish_data.py: Reads robot localization from TF and sends position data through serial communication to embedded hardware.<br>
test_serial.py: Utility script for testing serial communication and binary data transfer.

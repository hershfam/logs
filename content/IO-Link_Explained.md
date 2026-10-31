IO Link Explained: How Smart Sensors Communicate With PLCs

Most standard sensors don't give you much information. A proximity sensor tells the PLC whether something is there or not. An analog sensor sends a 4-20 mA signal that the PLC has to scale into an actual measurement.

IO Link takes that a step further. Instead of only getting a basic signal, you can communicate directly with the sensor and access additional information like diagnostics, settings, and device information.

Basically, it gives your PLC a lot more information to work with without completely changing how sensors are wired.

What Is IO Link?

IO Link is a standardized communication protocol that allows PLCs to communicate with sensors and actuators. It's based on the IEC 61131-9 standard.

One important thing to understand is that IO Link is not a fieldbus. It's a point-to-point connection, meaning each port on an IO Link master connects to one device.

It's also not tied to a specific PLC brand or network. The IO Link master handles communication with the sensors, then communicates with the PLC through an industrial network like EtherNet/IP, PROFINET, or EtherCAT.

Why Use IO Link?

There are a few pretty good reasons to use IO Link in an industrial environment:

- More information: Instead of just receiving a measurement, you can access additional sensor information and diagnostics.
- Remote configuration: Sensor settings can be changed through the PLC, HMI, or engineering software.
- Better troubleshooting: Sensors can report problems like overheating, short circuits, or buildup on the sensing surface.
- Easier replacement: When a sensor fails, the master can automatically transfer its saved settings to the replacement.
- Simpler wiring: Standardized cables and connectors make installation easier.
- Compatibility: You can use regular digital sensors alongside IO Link devices on the same master.

What Do You Need?

An IO Link system has a few main components.

1. IO Link Devices

These are the actual sensors and actuators connected to the system. Examples include pressure sensors, temperature sensors, RFID readers, valves, and motor starters.

2. IO Link Master

Think of the master as the middleman between your sensors and PLC. The sensors connect to individual ports on the master, and the master communicates with the PLC through the industrial network.

Masters are available for control cabinets (IP20) or direct machine mounting (IP65/IP67).

3. Cables and Connectors

One nice thing about IO Link is that it doesn't require special shielded communication cable. It uses standard three- or five-wire cables, typically with M12 connectors.

The maximum cable length between the device and master is 20 meters.

4. PLC

The PLC receives information from the IO Link master just like it would with other remote I/O. The main difference is how much additional information is available.

5. Configuration Software and IODD Files

IODD stands for IO Device Description. It's essentially a file that tells the configuration software what a particular sensor is capable of, what parameters it has, and what its data means.

Wiring and Communication

IO Link uses three main pins:

- Pin 1: 24V power
- Pin 3: 0V
- Pin 4: C/Q communication line

The C/Q connection is what makes IO Link different. It can operate as a standard digital input/output or carry digital IO Link communication.

There are two main port types:

- Class A: Standard port configuration. Pins 2 and 5 can have additional functions depending on the manufacturer.
- Class B: Provides an additional isolated power supply for devices that require more power.

A master can also operate ports in different modes. For example, you can have an IO Link pressure sensor on one port and a standard proximity sensor on another.

How Fast Is IO Link?

IO Link has three communication speeds:

- COM1: 4.8 kbaud
- COM2: 38.4 kbaud
- COM3: 230.4 kbaud

The actual update speed depends on the device and its minimum cycle time.

Cycle time is simply how often the master exchanges information with a sensor. Each device has a minimum cycle time listed in its IODD file.

This is important when selecting sensors because not every application needs the same response time.

Cyclic vs. Acyclic Data

This is probably one of the more important concepts to understand when working with IO Link.

There are two main types of communication:

Cyclic communication happens continuously at a set interval. This is where your normal process data comes from, such as pressure, temperature, or position.

Acyclic communication happens when information is requested or an event occurs. This is generally used for accessing settings, identification information, and diagnostics.

IO Link handles four main types of data:

- Process Data: The actual measurements or commands being exchanged between the PLC and device.
- Value Status: Indicates whether the process data is valid or invalid.
- Device Data: Information about the sensor, including its settings, identification, and diagnostic information.
- Events: Messages generated when something happens, such as overheating, a short circuit, or a communication failure.

For example, take an IO Link pressure sensor.

The actual pressure reading is sent continuously to the PLC. If you want to change the sensor's setpoint, that information is sent separately. If the sensor detects an issue, it can generate an event that the master passes along.

This allows you to monitor the actual process while still having access to additional sensor information.

Device Configuration and Replacement

One of the more useful features of IO Link is automatic device replacement.

The IO Link master can store a copy of a sensor's configuration. If that sensor fails and someone installs a replacement, the master can automatically transfer the saved settings to the new device.

This means you don't necessarily need a laptop or someone to manually configure the replacement sensor.

The master uses the IODD file and configuration software to manage device settings, assign ports, and map process data into the PLC.

Where Does IIoT Come Into Play?

IO Link itself isn't an IoT protocol. It handles communication between the sensor and master.

However, the master can also provide information to other systems outside the PLC.

Some masters support communication methods like:

- OPC UA: Allows other systems to access sensor measurements, settings, and diagnostics.
- MQTT: Allows data to be published to other systems using a lightweight messaging protocol.
- REST/JSON: Allows information to be exchanged with other applications through web-based interfaces.

This is where things get interesting.

Instead of only using sensor information for PLC control, you can also send it to historians, dashboards, or other monitoring systems.

For example, you could collect temperature trends, equipment runtime, or sensor diagnostics and use that information for condition monitoring and predictive maintenance.

Limitations of IO Link

IO Link is useful, but it isn't going to replace every industrial communication system.

A few limitations to keep in mind:

- Maximum process data is 32 bytes per direction.
- Maximum cable length is 20 meters between the device and master.
- Each device requires its own master port.
- It isn't designed for applications that require large amounts of data, such as cameras or high-speed scanners.

What to Look for When Choosing Equipment

If you're putting together an IO Link system, there are a few things worth checking before buying equipment:

- Make sure the master supports the same industrial network as your PLC.
- Check that the master supports the IO Link version required by your devices.
- Verify whether you need Class A or Class B ports.
- Make sure IODD files are available for your sensors.
- Check the minimum cycle time for each device.
- Look at the IP rating to make sure the equipment is suitable for its installation location.
- If you want to send data to other systems, check for OPC UA, MQTT, or REST support.

The Bottom Line

IO Link is basically a way to get more information out of the sensors you're already using in industrial automation.

Instead of only getting a digital signal or an analog measurement, you can access device settings, diagnostics, and additional process information through a single connection.

The IO Link master handles communication with the devices and passes that information to the PLC. From there, it can also be shared with other systems for monitoring and analysis.

For anyone working with PLCs, instrumentation, or industrial networking, it's worth understanding because it gives you a lot more visibility into what's actually happening out in the field.

Sources

Information referenced from the IO Link Community, Pepperl+Fuchs, ifm, Baumer, OPC Foundation, Analog Devices, ARC Advisory Group, and Banner Engineering.
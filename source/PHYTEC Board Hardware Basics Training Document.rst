.. START:section:6:0
**PHYTEC Board Hardware Basics - Training Document**
====================================================

.. END:section:6:0

.. START:main_content:6:0
**Purpose and scope**

| This document introduces the basic hardware concepts required when working with PHYTEC development boards. It covers:
|     • Basic SOM removal and installation precautions.
|     • Identification of the SOM, carrier board, connectors and peripherals.
|     • PHYTEC board families and their power-supply requirements.
|     • Official PHYTEC documentation sources for hardware verification.

.. END:main_content:6:0

.. START:list:6:0:0

.. LIST_META: {"type": "definition", "head": "", "items": ["**Understanding the hardware**", "~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~", "**System-on-Module (SOM)**", "A System-on-Module is a compact computer module that integrates the main processing components. Depending on the model, it may include: :: • Processor or system-on-chip (SoC). • RAM. • Non-volatile storage. • Power-management and supporting circuitry. • Interfaces routed to a module connector.", "The exact components depend on the SOM model.", "How to identify a SOM: :: 1. Look for the phyCORE product name. 2. Record the product number and module variant. 3. Record the PCB revision. 4. Find the matching SOM hardware manual on the official PHYTEC website. 5. Use the manual's component-placement diagram to identify the components."]}

**Understanding the hardware**
    

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    

**System-on-Module (SOM)**
    

A System-on-Module is a compact computer module that integrates the main processing components. Depending on the model, it may include:
    • Processor or system-on-chip (SoC). • RAM. • Non-volatile storage. • Power-management and supporting circuitry. • Interfaces routed to a module connector.

The exact components depend on the SOM model.
    

How to identify a SOM:
    1. Look for the phyCORE product name. 2. Record the product number and module variant. 3. Record the PCB revision. 4. Find the matching SOM hardware manual on the official PHYTEC website. 5. Use the manual's component-placement diagram to identify the components.

.. END:list:6:0:0

.. START:image:6:0:1

.. image:: _images/image_5.png

.. END:image:6:0:1

|

|

.. START:list:6:0:3

.. LIST_META: {"type": "enumerated", "head": "", "items": ["**Carrier board**", "The carrier board provides the physical interfaces and supporting circuitry required to use the SOM in a complete system.", "Depending on the carrier-board model, it may provide:", "• Power input.", "• Ethernet.", "• USB.", "• UART, RS-232 or RS-485.", "• CAN.", "• I²C and SPI expansion interfaces.", "• GPIO and PWM.", "• Display, camera and audio interfaces.", "• MicroSD or other storage connections.", "Not every carrier board exposes every processor interface.", "How to identify a carrier board:", "Look for the phyBOARD product name, where applicable.", "Record the carrier-board product number and PCB revision.", "Find the corresponding carrier-board hardware manual.", "Compare the board with the component-placement diagram.", "Match the connector labels and reference designators to the manual."]}

1. **Carrier board**
2. The carrier board provides the physical interfaces and supporting circuitry required to use the SOM in a complete system.
3. Depending on the carrier-board model, it may provide:
4. • Power input.
5. • Ethernet.
6. • USB.
7. • UART, RS-232 or RS-485.
8. • CAN.
9. • I²C and SPI expansion interfaces.
10. • GPIO and PWM.
11. • Display, camera and audio interfaces.
12. • MicroSD or other storage connections.
13. Not every carrier board exposes every processor interface.
14. How to identify a carrier board:
15. Look for the phyBOARD product name, where applicable.
16. Record the carrier-board product number and PCB revision.
17. Find the corresponding carrier-board hardware manual.
18. Compare the board with the component-placement diagram.
19. Match the connector labels and reference designators to the manual.

.. END:list:6:0:3

.. START:image:6:0:4

.. figure:: _images/image_6.png

   Fig 2 : Ex AM64 Carrier Board

.. END:image:6:0:4

|

.. START:list:6:0:5

.. LIST_META: {"type": "field", "head": "", "items": ["|", "**Complete development kit**", "A development kit commonly combines a SOM, carrier board and accessories.", "The external power input for the complete kit may differ from the voltage required by the SOM itself because the carrier board may contain voltage regulators.", "Important: Never assume that the SOM supply voltage is also the correct external input voltage for the complete development kit."]}

:|:
:**Complete development kit**:
:A development kit commonly combines a SOM, carrier board and accessories.:
:The external power input for the complete kit may differ from the voltage required by the SOM itself because the carrier board may contain voltage regulators.:
:Important: Never assume that the SOM supply voltage is also the correct external input voltage for the complete development kit.

.. END:list:6:0:5

.. START:image:6:0:6

.. figure:: _images/image_7.png

   | Fig 3 :  ex - phyBOARD®-Pollux
   | Imaging kit

.. END:image:6:0:6

|

.. START:list:6:0:7

.. LIST_META: {"type": "definition", "head": "", "items": ["|", "**SOM removal and installation precautions**", "~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~", "The correct extraction tool and mechanical procedure depend on the SOM connector and carrier-board design.", "**Before removing the SOM** :: 1. Shut down the operating system using the documented procedure. 2. Disconnect the external power supply. 3. Disconnect other connections that could back-power the board, where applicable. 4. Confirm the board is no longer powered before handling the module. 5. Use appropriate electrostatic discharge (ESD) protection, such as a grounded ESD wrist strap and ESD-safe work surface. 6. Identify the exact SOM and carrier board. 7. Read the relevant PHYTEC hardware manual and identify the required removal tool.", "**During removal** :: • Use the correct removal tool for the specific SOM connector. • Follow the prescribed removal points and procedure. • Apply controlled, even force. • Do not twist or bend the module. • Do not pull on components or use nearby components as leverage. • Stop if the module does not release as expected.", "**During installation** :: 1. Inspect the module and connector for visible damage or contamination. 2. Confirm the correct orientation. 3. Align the SOM with the carrier-board connector. 4. Seat the module evenly using the method specified by PHYTEC. 5. Do not force a misaligned connector. 6. Inspect the assembly before reconnecting power. 7. Reconnect power only after the module is correctly installed.", "**SOM removal video**", "The following video was supplied as a visual reference for the removal procedure:", "Watch the SOM removal procedure on YouTube", "Use the video together with the applicable PHYTEC hardware manual.", "The manual for the exact module and carrier-board combination should determine the tool and handling procedure.", "**Identifying connectors and peripherals**", "~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~", "Use the official carrier-board component-placement diagram and hardware manual to identify the connectors."]}

|
    

**SOM removal and installation precautions**
    

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    

The correct extraction tool and mechanical procedure depend on the SOM connector and carrier-board design.
    

**Before removing the SOM**
    1. Shut down the operating system using the documented procedure. 2. Disconnect the external power supply. 3. Disconnect other connections that could back-power the board, where applicable. 4. Confirm the board is no longer powered before handling the module. 5. Use appropriate electrostatic discharge (ESD) protection, such as a grounded ESD wrist strap and ESD-safe work surface. 6. Identify the exact SOM and carrier board. 7. Read the relevant PHYTEC hardware manual and identify the required removal tool.

**During removal**
    • Use the correct removal tool for the specific SOM connector. • Follow the prescribed removal points and procedure. • Apply controlled, even force. • Do not twist or bend the module. • Do not pull on components or use nearby components as leverage. • Stop if the module does not release as expected.

**During installation**
    1. Inspect the module and connector for visible damage or contamination. 2. Confirm the correct orientation. 3. Align the SOM with the carrier-board connector. 4. Seat the module evenly using the method specified by PHYTEC. 5. Do not force a misaligned connector. 6. Inspect the assembly before reconnecting power. 7. Reconnect power only after the module is correctly installed.

**SOM removal video**
    

The following video was supplied as a visual reference for the removal procedure:
    

Watch the SOM removal procedure on YouTube
    

Use the video together with the applicable PHYTEC hardware manual.
    

The manual for the exact module and carrier-board combination should determine the tool and handling procedure.
    

**Identifying connectors and peripherals**
    

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    

Use the official carrier-board component-placement diagram and hardware manual to identify the connectors.

.. END:list:6:0:7

.. START:table:6:0:8

.. csv-table::
   :header: "Interface", "Purpose", "What to verify in PHYTEC documentation"

   "Power input", "Supplies the complete board or kit", "Input voltage, current rating, connector and polarity"
   "Ethernet", "Wired networking", "Number and type of Ethernet ports"
   "USB", "Host or device connectivity", "Connector type and supported operating mode"
   "UART", "Serial communication and debugging", "UART instance, connector and signal levels"
   "RS-232", "Serial communication with external equipment", "Connector and transceiver details"
   "RS-485", "Differential serial communication", "Connector, transceiver and termination details"
   "CAN", "Controller Area Network", "Available CAN channels and transceiver circuitry"
   "I²C", "Peripheral communication", "Bus routing and connector pinout"
   "SPI", "Peripheral communication", "Bus routing, chip-selects and pin assignments"
   "GPIO", "Digital input/output", "Pin assignment, voltage limits and multiplexing"
   "PWM", "Pulse-width modulation", "Available channels and pin assignments"
   "MicroSD/eMMC", "Storage", "Removable slot or onboard storage details"
   "Display/camera/audio", "Multimedia interfaces", "Supported interfaces and connector details"

.. END:table:6:0:8

.. START:list:6:0:9

.. LIST_META: {"type": "enumerated", "head": "", "items": ["**Connector identification procedure**", "Record the board name and revision.", "Open the corresponding PHYTEC hardware manual.", "Find the component-placement diagram.", "Identify connector reference designators printed on the PCB.", "Match each connector to the manual.", "Check the pinout and electrical specifications before connecting external equipment.", "Record the official manual section or page used for verification.", "Do not assume that two physically similar connectors have the same pinout or electrical characteristics."]}

1. **Connector identification procedure**
2. Record the board name and revision.
3. Open the corresponding PHYTEC hardware manual.
4. Find the component-placement diagram.
5. Identify connector reference designators printed on the PCB.
6. Match each connector to the manual.
7. Check the pinout and electrical specifications before connecting external equipment.
8. Record the official manual section or page used for verification.
9. Do not assume that two physically similar connectors have the same pinout or electrical characteristics.

.. END:list:6:0:9

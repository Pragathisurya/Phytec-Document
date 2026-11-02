.. START:section:10:0
PHYTEC Embedded Linux | Basic concepts and build environment setup
==================================================================

.. END:section:10:0

.. START:main_content:10:0
| **Yocto Project**
| The Yocto Project is an open-source project that provides tools to build customized Linux operating systems for embedded devices. PHYTEC uses Yocto to develop Board Support Packages (BSPs) for its embedded hardware platforms.

A Board Support Package (BSP) contains the software and hardware-specific configuration required to run Linux on a particular board.

For example, when working with a PHYTEC board such as the phyBOARD-Nash i.MX93, Yocto can be used to build a Linux image configured for that hardware.

.. END:main_content:10:0

Important Points
~~~~~~~~~~~~~~~~

- Always select the PHYTEC BSP manual that matches your board and software release.
- Ensure that the target hardware configuration is correct before building.
- The initial build can take a long time and requires sufficient disk space.
- A successful build generates software images; it does not automatically flash them to the board.
- Follow the specific PHYTEC installation procedure before writing an image to an SD card or eMMC.

Use of Yocto
~~~~~~~~~~~~

- To build a Linux operating system for a specific embedded board.
- To customize the software packages included in the image.
- To configure the Linux kernel and root filesystem.
- To rebuild the software image when changes are required.

**Important Yocto Components**

.. START:table:10:0:2

.. csv-table:: The following terms are useful to understand before starting a build.
   :header: "Component", "Meaning"

   "BitBake", "The build engine that executes tasks to compile and assemble the software."
   "Recipe", "Instructions describing how a software component is built and installed."
   "Layer", "A collection of recipes and configuration metadata."
   "Poky", "The reference distribution and build system used by the Yocto Project."
   "phyLinux", "A PHYTEC tool used to initialize and manage the BSP source workspace."
   "BSP Image", "The resulting Linux software image prepared for the target board."

.. END:table:10:0:2

.. START:list:10:0:3

.. LIST_META: {"type": "bullet", "head": "", "items": ["MACHINE: Identifies the target hardware configuration.", "DISTRO: Defines the Linux distribution configuration."]}

- MACHINE: Identifies the target hardware configuration.
- DISTRO: Defines the Linux distribution configuration.

.. END:list:10:0:3

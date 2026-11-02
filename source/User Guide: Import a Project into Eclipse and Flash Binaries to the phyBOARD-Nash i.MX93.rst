.. START:section:9:0
**User Guide: Import a Project into Eclipse and Flash Binaries to the phyBOARD-Nash i.MX93**
============================================================================================

.. END:section:9:0

.. START:main_content:9:0
| Introduction
| This guide explains how to import an existing project into Eclipse, build the application, transfer the executable to the PHYTEC phyBOARD-Nash i.MX93, and install a bootable software image when required.

The procedure is based on the official PHYTEC Development Environment Guide and the PHYTEC i.MX93 BSP documentation.

.. END:main_content:9:0

.. START:list:9:0:0

.. LIST_META: {"type": "enumerated", "head": "", "items": ["Start the PHYTEC-provided virtual machine or the Linux development environment configured according to the PHYTEC Development Environment Guide.", "Open a terminal in the development environment.", "Confirm that Eclipse and the required cross-compilation SDK are installed.", "Select File → Import.", "Expand General.", "Select Existing Projects into Workspace.", "Click Next.", "Click Browse.", "Navigate to the directory containing the existing Eclipse project.", "Select the project directory.", "Confirm the selection and click Finish."]}

1. Start the PHYTEC-provided virtual machine or the Linux development environment configured according to the PHYTEC Development Environment Guide.
2. Open a terminal in the development environment.
3. Confirm that Eclipse and the required cross-compilation SDK are installed.
4. Select File → Import.
5. Expand General.
6. Select Existing Projects into Workspace.
7. Click Next.
8. Click Browse.
9. Navigate to the directory containing the existing Eclipse project.
10. Select the project directory.
11. Confirm the selection and click Finish.

.. END:list:9:0:0

Build the Project in Eclipse
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Building converts the project's source code into an executable for the target system.
Step 1: Select the Project
In Eclipse, locate and select the imported project in Project Explorer.
Step 2: Build the Project
1. Open the Project menu.
2. Select Build Project.
3. Observe the Console window for build messages and errors.
4. Confirm that the build completes successfully.
PHYTEC's development guide demonstrates cross-compiling a project to produce an executable for the target board.
Step 3: Identify the Output File
After a successful build, locate the executable produced by the project's build configuration.

The output depends on the project. It may be an executable or an ELF file, but not every .elf or .bin file is directly executable by Linux.

For a GUI application, confirm the expected executable and required resource files from the project's configuration.
5. Transfer the Executable to the Board

 **Transfer the Executable to the Board**
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

PHYTEC's Eclipse guide demonstrates transferring an executable to the target using Secure Copy (SCP).
Step 1: Establish the Network Connection
Configure the board and development computer according to the PHYTEC Quick Start Guide. The following is PHYTEC's documented example SSH command:
ssh root@192.168.3.11


The address is an example from the documented setup and may differ in your network configuration.
Step 2: Copy the Executable
PHYTEC demonstrates the transfer process with the following example:
scp ./myHelloWorld root@192.168.3.11:


Here, myHelloWorld is the example executable used in the PHYTEC guide. Replace it with the actual output filename from your project.

If the GUI application requires resource directories or other files, transfer those files according to the project's requirements.
Step 3: Run the Application
PHYTEC's example workflow includes executing the transferred program on the board:
ssh root@192.168.3.11 /root/myHelloWorld


Replace the example filename with your executable's actual name and location.

Confirm that the application starts successfully. For a GUI application, verify that the interface appears on the intended display.

Important: The example commands are documented for PHYTEC's demonstration application. GUI Guider-specific launch settings, libraries, and display configuration are not fully described in the cited Eclipse guide.

Flash a BSP Image to an SD Card or eMMC
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Flashing a complete operating-system image is different from copying an application executable to the board.

PHYTEC's i.MX93 BSP documentation describes installing bootable images and configuring the board to boot from the intended storage device.
Step 1: Obtain the Correct BSP Image
Download the appropriate BSP image for the phyBOARD-Nash i.MX93 and the required BSP release from the official PHYTEC resources.

PHYTEC documents bootable WIC images and supported update packages for its BSP installation procedures.
Step 2: Identify the SD Card Device
When preparing an SD card on a Linux host, run:
lsblk


Identify the correct storage device before proceeding. Selecting the wrong device can erase important data.
Step 3: Write the WIC Image
For an uncompressed WIC image, PHYTEC documents this general command pattern:
sudo dd if=<image>.wic of=/dev/<your_device> bs=1M conv=fsync status=progress


Replace <image>.wic with the actual image filename and /dev/<your_device> with the correct SD-card device.

For a compressed WIC image, the documented command pattern is:
xzcat <image>.wic.xz | sudo dd of=/dev/<your_device> bs=1M conv=fsync status=progress


These operations write the image to the selected device and can erase its existing contents. Verify the image filename and target device before executing either command.
Step 4: Configure the Boot Source
PHYTEC's BSP documentation describes using the board's boot-mode switch (S3) to select the intended boot source.
1. Configure S3 according to the official phyBOARD-Nash documentation.
2. Insert the prepared SD card if booting from SD.
3. Connect the serial debug console.
4. Power on the board and observe the boot messages.
PHYTEC documents the USB-C debug connection X37 and serial settings of 115200 baud, 8 data bits, no parity, and 1 stop bit (8N1).
Step 5: Understand eMMC Flashing
The BSP manual provides separate instructions for installing software to eMMC. Follow that procedure for the exact BSP version and image format.

Do not write a GUI application's .elf or .bin file directly to the eMMC as if it were a complete bootable operating-system image.

For a normal GUI application, the usual workflow is to build the executable, transfer it to the existing Linux filesystem, and run it. Reflashing the operating system is necessary only when installing or replacing the bootable software image.

Verification Checklist
~~~~~~~~~~~~~~~~~~~~~~

Before completing the procedure, verify the following:
- The BSP and SDK major versions are compatible.
- The project has been imported into Eclipse.
- The application builds successfully for the target architecture.
- The expected executable has been generated.
- The executable and required resources have been transferred to the board.
- The application runs successfully on the board.
- If an operating-system image was installed, the correct BSP image and documented flashing procedure were used.

Official PHYTEC References
~~~~~~~~~~~~~~~~~~~~~~~~~~

1. PHYTEC Development Environment Guide – Working with Eclipse:
   https://www.phytec.de/cdocuments/?doc=poDMMg
2. PHYTEC i.MX93 BSP Manual – BSP installation and configuration:
   https://phytec.github.io/doc-bsp-yocto/bsp/imx9/imx91-93/pd24.2.2.html
Documentation note: The Eclipse import, cross-compilation, executable transfer, and BSP image installation procedures above are based on PHYTEC documentation. GUI Guider-specific project configuration and resource requirements are not explicitly covered in the cited guides and must be verified against the generated project.

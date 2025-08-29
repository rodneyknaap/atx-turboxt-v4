# atx-turboxt-v4
ATX Turbo XT highly integrated PC mainboard

# Revision 4 design of a PC/XT mainboard based on CPLD technology  
The project will use CPLD technology to replace as many TTL ICs as possible in the IBM PC/XT design.  
In addition as further development goals once the prototype is running, we will attempt to eliminate the need for a 8284 and 8288 and replace these functions with CPLD technology. Further we will attempt to make more upgrades and modifications to the XT system control.  

So the main goal of this project is greatly reducing the XT computer in a smaller number of ICs and total PCB area.  
Beyond that we want to improve the system control.  

## Purpose and permitted use, cautions for a potential builder of this design
This project was created for historical purposes out of love for historical computing designs and for the purpose of enabling computing enthousiasts with a sufficient level of building and troubleshooting expertise to be able to experience the technology by building and troubleshooting the hardware described in this project. Due to the level of this project, it may be suitable as a project for students to get into. If there are any questions from teachers who like to teach about this technology I would be happy to answer them. It may be really interesting to analyse the elaborate and complex CPU timing and 8 bit to 16 bit data byte translation and DMA mechanisms in an educational setting.

Besides the GPL3 license there are a few warnings and usage restrictions applicable:
No guarantees of function or fitness for any particular or useful purpose is given, building and using this design is at the sole responsibility of the builder.

Do not attempt this project unless you have the necessary electronics assembly expertise and experience, and know how to observe all electronics safety guidelines which are applicable.

It is not permitted to use the computer built from this design without the assumption of the possibility of loss of data or malfunction of the connected device. To be used strictly for personal hobby and experimental purposes only. No applications are permitted where failure of the device could result in damage or injury of any kind.

If you plan to use this design or any part of it in new designs, the acknowledgement of the designer and the design sources and inspirations, historical and modern, of all subparts contained within this design should be included and respected in your publication, to accredit the hard work, time and effort dedicated by the people before you who contributed to make your project possible.

No guarantee for any proper operation or suitability for any possible use or purpose is given, using the resulting hardware from this design is purely educational and experimental and not intended for serious applications. Loss of data is likely and to be expected when connecting any storage device or storage media to the resulting system from this design, or when configuring or operating any storage device or media with the system of this design.

When connecting this system to a computer network which contains stored information on it, it is at the sole responsibility and risk of the person making the connection, no guarantee is given against data loss or data corruption, malfunctions or failure of the whole computer network and/or any information contained inside it on other devices and media which are connected to the same network.

When building this project, the builder assumes personal responsibility for troubleshooting it and using the necessary care and expertise to make it function properly as defined by the design. You can email me with questions, but I will reply only if I have time and if I find the question to be valid. Which will probably also lead to an update here. I want to primarily dedicate my time to new project development, I am not able to do any user support, so that's why I provide the elaborate info here which will be expanded if needed.

# Project outline
After designing several generations of PC/AT computers, more insight and experience has been gained, which will now be reinvested to attempt to further improve the revision 3 XT PC design.  

For the XT memory we will use a single SRAM IC and move the SRAM data bus onto the X-data bus, thus eliminating the memory data bus.
The X-address bus will serve all the onboard circuits, while the normal address bus will drive the slot cards.

The I/O and memory decoding will be taken over by CPLD technology.  
We will wire the CPLD in parallel to the 8284 and 8288 so only reprogramming and disconnecting the 8284 and 8288 pins will be needed to experiment with taking over the READY, CPU RESET, and the command generation on signal by signal development basis.

Generation of HLDA from the CPU status and DMA arbitration will be revised to attempt to create separate DMA timing which is independent of the CPU clock speed.
The DMA timing will run at the DMAC relevant speed while the CPU will be able to run faster.

Further, we will attempt to experiment with certain mechanisms from the PC/AT design to test and apply these on the XT design.
Examples of this are DMA arbitration and wait state mechanisms.
All the timing sensitive logic will be created inside CPLDs so we will gain a set design that is no longer depentent on logic speeds of TTL ICs.
Depending on how many CPLD pins will be available, we may also develop a CPLD version of XT-IDE logic in an attempt to gain a set timing design for the conversion mechanisms used in the XT-IDE interface and XT-IDE Universal BIOS.

# Project status  
- the project is under development and currently the mainboard schematic is being revised from Rev3 to Rev4.
- preparation is ongoing to migrate functions into one or more CPLDs and removing these from the mainboard.

Kind regards,

Rodney

Last update: 29-8-2025

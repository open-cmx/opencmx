# openCMX

## General Information

openCMX (Open Compute Module Extended) is a proposed Open Source, standardized, modular form factor and I/O specification for small, scalable, system on module computing devices.

**Goals**

The goal of openCMX is to establish an open-source system on module form factor and connection scheme for small low powered devices that allows an individual to use cost effective USB-C hubs and docks to fully operate the module. In addition to this scenario, the user may also use the same module(s) along with 3rd party designed backplanes, to scale the same module(s) to high density clusters.
Some examples of openCMX usaage:

- Home hobbyist
- Embedded Media Applications
- Commercial Thin Clients and low powered desktops
- Industrial embedded applications
- Robotics Development
- Education and Developing Counties
- Homelab Certification
- Large cluster development and testing

**Basics**

- The form factor is built upon the [15mm 2.5" U.2 storage physical specifications](https://www.snia.org/forums/cmsi/knowledge/formfactors#u2). This form factor is well established with OEMs and makes use of existing accessories and chassis tooling. 
- Primary I/O is dependent on reuse of the U.2 SFF-8639 connector to carry a PCIe x4 connection as well as a USB 3.2 connection for power, peripherals, and display output. The use of this edge connector allows for scalability within high density rack enclosures as well as smaller clusters without the need for external power supplies, network switches, etc. 
- In conjunction with the SFF-8639 connection, a second USB 3.2 port (USB-C) is used for use with commodity USB-C Hubs. 
- openCMX modules can be used either as a bare PCB with user customized SoC cooling etc. The module can also reside within an aluminum enclosure doubling as a heatsink. This adds durability and essential heat transfer when in higher density clusters. 
- The user only pays for the I/O they want (USB-C Hubs, Docks, backplanes). Once the user invests in a chassis and I/O, modules can be swapped or upgraded without any physical reconfiguration (cables, power supplies, etc)
- Conforms to [USB-C Power Delivery specification](https://www.usb.org/document-library/usb-power-delivery) to accept between 9v-20v at various USB-C PD profiles. 

## Requirements

**Compliant I/O**

Each openCMX module must include:

- 1x SFF-8639 connector carrying PCIe x4 and USB 3.2 (USB Power Delivery Compliant, Display-Alt-Mode) [Pinout TBD]
- 1x USB-C 3.2 (Mid-Mount) installed adjacent to the SFF-8639 connector
- 1x 4-Pin JST PWM Fan header [Connector specifications TBD]

**Physical Requirements**

Each openCMX compliant module must conform to the following physical specifications:

- PCB must fit within an enclosure that conforms to the specifications of a 2.5” u.2 SSD. See “U.2 Mechanical Spec.pdf” for rough external measurements.

- No I/O connectors are to be present along the "long" sides of the PCB. I/O can only be present along the "short" edges of the PCB.

- No I/O connector shall protrude past the module enclosure as described the in "U.2 Mechanical Spec.pdf"

- Total Z height of pcb, plus components should not exceed 13mm (to account for enclosure)

 - Components which generate above 50% of the total heat output of the complete module should be located on the “Thick” side of the PCB. Will be known as “Side A.” SOC, Memory, Etc… Enclosure acts as a heatsink for these components when in high density rack environments.

- Components on the Thin Side, otherwise known as “Side B” cannot exceed the height of the SFF-8639 connector as it protrudes from the PCB. 

**Operational Requirements**

- Each openCMX module must have at least one on-board mass storage device capable of being used as an operating system boot device. Note - soldered eMMC or other permanently attached mass storage may be substituted if manufacturer wishes not to include user replaceable storage interfaces.  

- Applying power to the device either through the USB-C 3.2 or SFF-8639 connector will trigger a boot up sequence with no user interaction. 

- No physical device(s) shall be used to trigger a module power event such as Power On, Power Cycle, etc.

- openCMX module must be powered via USB Power Delivery 9v-20v negotiation based on specific needs. Both the USB-C and SFF-8639 connection can accept USB-PD Input.

- Both USB-C and SFF-8639 connections are to support standard USB based Display Alt Mode (pinout TBA)

- An openCMX module total TPD is not to exceed 25w. 

## Design Concept Illustrations
- Only required components are shown (excluding SOC)
  
**Side A**

![opencmx](https://github.com/dontthroworanges/opencmx/blob/main/openCMX_SideA.png)

**Side B**

![opencmx](https://github.com/dontthroworanges/opencmx/blob/main/openCMX_SideB.png)

## Basic Dimensions

![opencmx](https://github.com/dontthroworanges/opencmx/blob/main/openCMX_BasicDimensions.png)


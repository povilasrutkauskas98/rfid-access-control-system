## Hardware Design

The access control system was designed to read RFID/NFC identification cards, process the received data, and transmit access events over an Ethernet network for monitoring and logging purposes.

### Power Supply

The system is powered from a 12 V DC source. A regulated 3.3 V supply rail is generated using an LM317 adjustable voltage regulator, providing power for the microcontroller, RFID reader, and Ethernet interface.

The output voltage was calculated according to the LM317 datasheet and configured for 3.3 V operation using an external resistor divider. Additional filtering capacitors were added to reduce power supply noise and improve system stability.
<img width="808" height="339" alt="image" src="https://github.com/user-attachments/assets/f0272a57-2ce6-4236-a204-c2beceac621a" />


### Ethernet Interface

Network communication is implemented using the ENC28J60 Ethernet controller connected via the SPI interface.

Several Ethernet solutions were evaluated during development, including ENC28J60, W5100, and LAN8720. The ENC28J60 was selected due to its availability, low cost, and straightforward SPI integration.

Key features:

* SPI communication interface
* Integrated MAC and PHY
* RJ45 Ethernet connectivity
* 10 MHz crystal oscillator
* External network access for event reporting
 <img width="951" height="676" alt="image" src="https://github.com/user-attachments/assets/0e3f11fb-ffad-47bc-9e39-ddc6b4e60d90" />


### Microcontroller

The main controller of the system is the STM32F407VG microcontroller.

Several STM32 devices were evaluated during the design phase, including STM32F103C8 and STM32L053R8. The STM32F407VG was selected due to its higher processing performance and significantly larger memory resources.

Key specifications:

* ARM Cortex-M4 core
* Operating frequency up to 168 MHz
* 1 MB Flash memory
* 192 KB SRAM
* Multiple SPI interfaces
* Integrated Ethernet MAC

The microcontroller is responsible for:

* Reading RFID card identifiers from the ST25R3911 reader
* Processing user identification data
* Managing Ethernet communication
* Serving a web interface for access event visualization
<img width="614" height="546" alt="image" src="https://github.com/user-attachments/assets/f713a96c-c390-44d7-8e7d-c4b4fda486bc" />


### RFID Components

The RFID subsystem consists of:

* ST25R3911 RFID/NFC reader IC
* ST25TV passive NFC/RFID tag
* Custom-designed 13.56 MHz PCB antennas

Communication between the reader and identification card is performed using ISO15693 and ISO18000-3 standards.

